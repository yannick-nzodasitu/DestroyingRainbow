# Bet X Factor

## Feature: Sign in
    User sign in to the website

### Background:
    Given users have an account on the website
    And the users are at the sign in page
    
1. Scenario: Anonymous user input their credential
    Given the users could see text fields to enter their username and password
    And these text fields are empty
    And the sign-in button is gray and unclickable as they have not entered their credentials
    When they input their username and password
    Then they should see their password replaced by "*"
    And the color of the button should be changed from gray
    And the user should be able to click the button
    
2. Scenario: Anonymous user confirm sign in - correct credential
    Given users have entered their username and password
    And their credentials are correct
    When they click the sign-in button
    Then they will be redirected to the main page as an authenticated user

3. Scenario: Anonymous user confirm sign in - wrong credential
    Given users have entered their username and password
    And their credentials are wrong
    When they click the sign-in button
    Then they will remain at the sign-in page
    And the border of the text field for username and password should change to red
    And there should be an error message saying the username or password is wrong


## Feature
4. Scenario: Anonymous user can create a profile


- Profile creation includes following informations:
  - Full name
  - Email address
  - Credit Card
- Credentials informations should be verified in two ways:
  - Frontend:
    - Correct format of an email address
    - Validate credit card information
  - Backend:
    - See if email exists in database


3. Scenario: User should see daily odds on the main page.
    Given a user enters the website 
    then they should be presented with daily odds of all games

4. Scenario: User tries to withdraw after the time to bet has expired.
    Given a user is authenticated
    Then they should be presented an error window saying that the time for bet is over

5. Scenario: User should see overall performance
    Given a user is logged in to the  website 
    And they are authenticated
    then they should be presented with their overall performance(percentage wins and loss)

6. Scenario : A user logs in and should see their current bet 
    Given a user enters on the website
    And the are authenticated
    They should be presented with information if the are losing or winning current bet
    

7. Scenario: udapte profil 
 Given a user view profile
 When he need to edit the user profil
 Then is renames and saves it.
 


8. Scenario: User should be able to see pass match up history
Given a user enters the website 
And they are presented with all matchups for the daily
And they are presented with all odds for the day
Then they should be able to select a certain game to bet on 
When selecting the game to bet on 
Then they should be presented with previous matchup history between the two teams


9. Scenario: User should be presented with rivalary information
Given a user enters the website 
And they are presented with all matchups for the daily
And they are presented with all odds for the day
And the two teams that are playing are rivals
Then user should be presented with information showing that the teams are rivals.


10. Scenario: User tries to enter on the bet when its time has already expired 
    Given a user is logged on the website
    And they are authenticated
    They will get a message  that the time to place bets is over
    And the will return bacto the page where there are open bets

11. scenario: undo the user profil change
Given a user view profile
Then edit the user profile
Then Undo user profile editing 
Then Out of database
