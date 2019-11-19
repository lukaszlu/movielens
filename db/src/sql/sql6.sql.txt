select reco_count, count(1) as user_count
from (
  select userid, max(rank) as reco_count
  from "aa.movielens.db.hdb.apl.views::recommendation_collaborative"
  group by userid
) group by reco_count order by 1 desc;