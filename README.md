# hello-world
This is my first repository

Hi humans!

I am Xun Peng. A graduate student have great passion for programming!


SELECT event as issue_status, COUNT(*) as cnt FROM (
  SELECT type, repo.name, actor.login,
    JSON_EXTRACT(payload, '$.action') as event, 
  FROM (TABLE_DATE_RANGE([githubarchive:day.], 
    TIMESTAMP('2011-02-01'), 
    TIMESTAMP('2011-03-01')
  )) 
  WHERE type = 'IssuesEvent'
)
GROUP by issue_status;
