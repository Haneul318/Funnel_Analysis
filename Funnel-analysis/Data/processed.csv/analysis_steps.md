

-- ---------------------------------------------------------------
-- Goal:
--  - Count total users per stage
--  - Calculate cumulative conversion rate
--  - Calculate step conversion rate
--  - Calculate drop-off rate between stages

---------------------------------------------------------------



CREATE TABLE funnel_analysis AS
SELECT
    stage,                                             -- Funnel stage name (e.g., homepage, cart, purchase)
    COUNT(DISTINCT user_id) AS users,                  -- Number of unique users at this stage

    -- Cumulative Conversion Rate:
    -- = (Users at this stage ÷ Users at homepage) * 100
    ROUND(
        100.0 * COUNT(DISTINCT user_id) 
        / MAX(COUNT(DISTINCT user_id)) OVER (), 2
    ) AS cumulative_conversion_rate,

    -- Step Conversion Rate:
    -- = (Users at this stage ÷ Users at the previous stage) * 100
    ROUND(
        100.0 * COUNT(DISTINCT user_id)
        / LAG(COUNT(DISTINCT user_id)) OVER (ORDER BY MIN(stage_order)),
        2
    ) AS step_conversion_rate,

    -- Drop-off Rate:
    -- = 100% - Step Conversion Rate
    ROUND(
        100.0 - (
            100.0 * COUNT(DISTINCT user_id)
            / LAG(COUNT(DISTINCT user_id)) OVER (ORDER BY MIN(stage_order))
        ),
        2
    ) AS drop_off_rate

FROM user_data_clean
GROUP BY stage
ORDER BY MIN(stage_order);


-- Check the summarized funnel data
SELECT * FROM funnel_analysis;



