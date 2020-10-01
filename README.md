# ASR-java

SELECT
    subregion1_name AS state,
    SUM(cumulative_confirmed) AS total_confirmed_cases
FROM
    `bigquery-public-data.covid19_open_data.covid19_open_data`
WHERE
    country_name="United States of America"
    AND date = "2020-04-10"
GROUP BY subregion1_name
HAVING total_confirmed_cases > 1000
ORDER BY total_confirmed_cases DESC
