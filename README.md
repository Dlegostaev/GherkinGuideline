# GherkinGuideline
### This is a Gherkin Guideline made by Dmitry Legostaev

> **Indent:** 2 spaces

**Indent structure:**
Feature keyword = 0 indents
Feature description = 1 indent

_Rule keyword = increase all related lines to that rule by 1 indent_

Background keyword = 1 indent

Scenario tags = 1 indent
Scenario keyword = 1 indent
Scenario outline keyword = 1 indent

Given, When, Then keywords = 2 indents
And, But keywords = 3 indents

Examples keyword = 2 indents
Examples table = 3 indents

Step table = step indent + 1

**Newline structure:**
Between Feature and Single-line Description = 0 newlines
Between Feature and Multi-line Description = 1 newline
Between Feature and Scenario Tags/Scenario/Scenario Outline = 1 newline
Between Scenario Tags/Scenario last step/Scenario Outline last step and Scenario Tags/Scenario/Scenario Outline = 2 newlines
Between Scenario/Scenario Outline line and first step line = 0 newlines
Between scenario lines = 0 or 1 newlines depends on step grouping
After last step of last scenario = 1 newline


**Tags:** each tag on a newline, but tag grouping is available at the same line

**Step signature:**
Pattern words is lowercase
Element and Parameter words are Title Case

Given: past tense action "I did Something" or define the state by "I am on Some Page"/"I am an Admin user"
When: present tense "I do Something"
Then: present tense "I assert Something"

If application have different places to do the same thing, define place explicitly like: "I click Back on Personal Account Page"


Example:
```gherkin
Feature: GuidelineFeature
  This feature represent simple example of Gherkin Guideline by Dmitry Legostaev

  Background:
    Given I am a QA Automation Engineer in Agile team
      And I have a GitHub account
      And I am logged in

  @GitHub
  @Search
  @JIRA-152
  Scenario: Search for Gherkin Guideline from Main Page
    Given I am at GitHub Main Page
    When I search for <Search Text> at Top Navigation Bar
      | Gherkin Guideline  |
      | Gherkin Guidelines |
    Then I see GitHub Search Results page
      And I see GherkinGuideline repo in the results


  @GitHub
  @Search
  @JIRA-153
  Scenario Outline: Search for Gherkin Guideline from My Profile Page
    Given I am at GitHub My Profile Page
    When I search for <Search Text> at Top Navigation Bar
      | Search Text        |
      | Gherkin Guideline  |
      | Gherkin Guidelines |
    Then I see GitHub Search Results page
      And I see GherkinGuideline repo in the results
      
  @GitHub
  @Search
  @JIRA-154
  Scenario Outline: Search for Gherkin Guideline from My Profile Page - negative
    Given I am at GitHub My Profile Page
    When I search for <Search Text> at Top Navigation Bar
      | Search Text |
      | C#          |
      | Java        |
    Then I see GitHub Search Results page
      But I don't see GherkinGuideline repo in the results

```

