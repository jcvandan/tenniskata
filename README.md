# The Kata

Your task is to write a `TennisGame` class containing the logic which outputs the correct score as a string for display on the scoreboard.

When a player scores a point, it triggers a method to be called on your class letting you know who scored the point.

Later, you will get a call `Score()` from the scoreboard asking what it should display. This method should return a string with the current score. Tennis scores are summarized below:

- Scores from zero to three points are described as '0', '15', '30', and '40' respectively.
- If at least three points have been scored by each player, and the scores are equal, the score is 'Deuce'.
- If at least three points have been scored by each side and a player has one more point than his opponent, the score of the game is 'Advantage' for the player in the lead.
- If a player has won at least four points in total and at least two points more than the opponent, then `Score()` should output the message 'Player N Wins'

## Example test cases

Here are some example test cases to get you started (pardon my terrible cases):

```
Given   I have a tennis game
When    Neither player has scored a point
Then    Score should return "0 - 0"

Given   I have a tennis game
When    Player 1 has scored a point
And     Player 2 has not scored a point
Then    Score should return "15 - 0"
```
``` C#
[Fact]
public void NoPoints_ShouldBe_LoveLove()
{
  var tennisGame = new TennisGame();
  Assert.Equal(tennisGame.Score(), "0 - 0");
}

[Fact]
public void PlayerOne_Score1_Player2_Score0_ShouldBe_FifteenLove()
{
  var tennisGame = new TennisGame();
  tennisGame.Player1Scored();
  Assert.Equal(tennisGame.Score(), "15 - 0");
}
```