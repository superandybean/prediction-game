# DPC Predicting Game

## Are you good at predicting DPC matches? 

Come find out on the DPC Predicing Game [here](https://dpc-predictions-game.herokuapp.com/)! This game was inspired by [FiveThiryEight's NFL Forecasting Game](https://projects.fivethirtyeight.com/2021-nfl-forecasting-game/).

## How it Works

After logging in through Steam, you may predict upcoming matches on the [upcoming matches](https://dpc-predictions-game.herokuapp.com/upcoming_matches) page. Use the sliders to predict the winner of the match. However, this is not just a simple who wins challenge. You must predict the probability of the team winning, and the points lost or gained depends on that probability, determined by [Brier scores](https://en.wikipedia.org/wiki/Brier_score). The points from each match range from a gain of 25 points to a loss of 75 points, and is determined using the formula          

```points = 25 - (([probability of team winning] - 100)^2 / 100)```

For example, let's say for the Team Liquid vs Nigma Galaxy match, you predict that Nigma Galaxy has a 73% chance of winning. Then, if Nigma Galaxy does indeed win, you will gain 17.7 points! However, if Team Liquid wins, you will lose 28.3 points.         
Nigma Galaxy did end up [winning](https://www.dotabuff.com/matches/6371895283) the match 2-1, so you would've have gained 17.7 points.            

Find every completed match at the [completed matches](https://dpc-predictions-game.herokuapp.com/complete_matches) page, along with the average guess and points and your guess and points, if applicable.      

Find the top scorers and your rank on the [leaderboard](https://dpc-predictions-game.herokuapp.com/leaderboard) page! The number of correct picks is used as a tiebreaker if there is a tie between scores.

## Technologies Used

This site uses [ExpressJS](https://expressjs.com/) and is hosted on [Heroku](https://www.heroku.com/). [mongoDB](https://www.mongodb.com/) was used for the database. Account authentication uses [Steam](https://steamcommunity.com/dev) and [OpenID](https://openid.net/connect/). Team logos are from the [OpenDota API](https://docs.opendota.com/) and the match data is from the [Liquipedia API](https://liquipedia.net/api-terms-of-use).        
[handlebars](https://handlebarsjs.com/) and [Tailwind CSS](https://tailwindcss.com/) was used for the frontend. The sliders were from the [noUISlider](https://refreshless.com/nouislider/) library.

## Possible Improvements

- [x] Sort upcoming matches by start time
- [x] Add predictions for tiebreaker matches
- [ ] Add league filtering on the leaderboard
