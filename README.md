# Rails Practice

## Setup

* `bundle`
* `rake db:create db:migrate db:seed`
* `rails s`

You can run specs with:

* `rspec`

Note: email/password combinations for existing users populated by `rake db:seed` can be found in the db/seeds.rb file.

## Stories

**User can add a task**
```
As a user
When I log in I should see a "new task" link next to each task list name
When I click that link, I should see a description field and a date field (w/ year / month / day dropdowns)
When I fill in a description and click "Create Task" I should see the task appear beneath the task list
And I should see a flash message that reads "Task was created successfully!"
Each task should have the due date represented in relative time
```

**User must fill in description on all tasks**
```
As a user
When I am adding a task
And I don't fill in the description field
And I press "Create Task"
Then I should see a message that reads "Your task could not be created" (in maroon)
And the label for the description field should be maroon.
```

**Users can complete tasks**
```
As a user
When I go to the task lists page I should see a button to "Complete" every task
When I press that button, the task should be removed from the page
NOTE: we don't want to delete tasks from the database - just hide completed tasks from users
```

**Tasks must appear in order of their due date**
```
As a user
When I create multiple tasks in a list
Then I should see them in chronological order
```

**Task lists with empty tasks should show a friendly message**
```
As a user
When I see a task list with no tasks
Then I should see a message that reads "Nothing here to see!"
```

**Users should be able to assign tasks to users**
```
As a user
When I create a new task
I can optionally add a user to the task
And when a user is assigned a task, I can see that user on the index page
```

**Users can filter tasks assigned to a particular user from the index page**
```
As a user
When I go to the homepage
And I select a user's name from a dropdown and click "filter"
Then I should see only tasks that are assigned to that user
```

## Wireframes

Task lists page:

<img src="project/01-index.png">

New task page:

<img src="project/02-new.png">

New task page w/ errors:

<img src="project/03-new-with-errors.png">

Flash message:

<img src="project/04-flash-message.png">

New form with user:

<img src="project/05-new-with-user.png">

Index page with filter:

<img src="project/06-index-with-assignees.png">

## References

* [Flash](http://guides.rubyonrails.org/action_controller_overview.html#the-flash)
* [Date Select](http://api.rubyonrails.org/classes/ActionView/Helpers/DateHelper.html#method-i-date_select)
* [Validations in views](http://guides.rubyonrails.org/active_record_validations.html#displaying-validation-errors-in-views)
