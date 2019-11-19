select
    count(1) as movie_count
  , count(1) * 100 / (select count(1) as cnt from "aa.movielens.db.data::movies" ) as movie_ratio
from (
  select movieid
  from "aa.movielens.db.hdb.apl.views::recommendation_contentbased"
  group by movieid
);