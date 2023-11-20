# Quiz API

This API provides endpoints for creating and answering quizzes.

This project is Ruby on Rails 7 API only project with SQLite database and Ruby 3.1.X

Here's what's already installed:
- Byebug
- RSpec
- Rubocop

# Requirements

1. Implement a Quiz model with attributes: title and description.
3. Implement a Question model with attributes: title, options, correct_answer.
4. Implement an Answer model with attributes: value and correct (a boolean indicating if the answer is correct).
5. Set up associations between the models: a Quiz has many Questions, a Question belongs to a Quiz, a Question has many Answers, and an Answer belongs to a Question.
6. Create CRUD API endpoints for managing quizzes, questions, and answers.

## Quiz endpoints:

- POST /quizzes - Create a new quiz.
- GET /quizzes - Retrieve a list of all quizzes.
- GET /quizzes/:id - Retrieve a specific quiz by ID.

Nice to haves:
- PATCH /quizzes/:id - Update a specific quiz.
- DELETE /quizzes/:id - Delete a specific quiz.

## Question endpoints:

- POST /quizzes/:quiz_id/questions - Create a new question for a specific quiz.
- GET /quizzes/:quiz_id/questions - Retrieve all questions for a specific quiz.
- GET /questions/:id - Retrieve a specific question by ID.

Nice to haves:
- PATCH /questions/:id - Update a specific question.
- DELETE /questions/:id - Delete a specific question.

## Answer endpoints:

- POST /questions/:question_id/answers - Create a new answer for a specific question.
- GET /questions/:question_id/answers - Retrieve all answers for a specific question.
- GET /answers/:id - Retrieve a specific answer by ID.

Nice to haves:
- PATCH /answers/:id - Update a specific answer.
- DELETE /answers/:id - Delete a specific answer.

## Important

- The quizzes routes are already defined in `routes.rb`.

```
 quiz_questions GET    /quizzes/:quiz_id/questions(.:format)                                                             questions#index
                POST   /quizzes/:quiz_id/questions(.:format)                                                             questions#create
  quiz_question GET    /quizzes/:quiz_id/questions/:id(.:format)                                                         questions#show
                PATCH  /quizzes/:quiz_id/questions/:id(.:format)                                                         questions#update
                DELETE /quizzes/:quiz_id/questions/:id(.:format)                                                         questions#destroy
   quiz_answers GET    /quizzes/:quiz_id/answers(.:format)                                                               answers#index
                POST   /quizzes/:quiz_id/answers(.:format)                                                               answers#create
    quiz_answer GET    /quizzes/:quiz_id/answers/:id(.:format)                                                           answers#show
                PATCH  /quizzes/:quiz_id/answers/:id(.:format)                                                           answers#update
                DELETE /quizzes/:quiz_id/answers/:id(.:format)                                                           answers#destroy
        quizzes GET    /quizzes(.:format)                                                                                quizzes#index
                POST   /quizzes(.:format)                                                                                quizzes#create
           quiz GET    /quizzes/:id(.:format)                                                                            quizzes#show
                PATCH  /quizzes/:id(.:format)                                                                            quizzes#update
                DELETE /quizzes/:id(.:format)                                                                            quizzes#destroy
```

- The quizzes controller is already created with empty actions for each endpoint.
- Ensure that the API returns JSON responses.
- Implement any necessary error handling.
- At least one endpoint shoudl be covered with tests.
