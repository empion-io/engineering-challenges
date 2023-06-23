# Empion - Full-Stack Challenge

## Context

On our mission to automate headhunting and connect applicants with the best company cultures, a customer of ours requested a new product. The Empion Culture Matcher.

## Your goal

Your goal is to create a full-stack application - the Empion Culture Matcher.

The application should be composed of:

- A Backend API
- A Web client

## Delivery

We expect you to deliver the soultion in a public Github repository. We should be able to clone this repository and run the solution based on the instructions.

### Time investment and planning

We appreciate you are investing your time to work on this solution. We don't wan't you to create a production ready application, therefore, keep in mind the principle of "make it work, make it right, make it fast/pretty". 

It should be your priority to deliver a functional, and as complete as possible, solution first, followed by a sophisticated/super well architected solution, followed by outstanding UX.

The decision of when to stop and consider your solution ready to deliver is up to you. However, pay attention to the evaluation criteria described below. The more your solution aligns with the evaluation criteria, the better your evaluation will be.

## Evaluation criteria

- Completeness: Were all the requirements implemented? If not, the partial solution is coherent and functional?
- Documentation: Is the project documented? Were we able to run the solution based on the given instructions?
- Architecture: Is the solution overengineered? Were the architecture decisions justified in the documentation?
- Quality: Is the solution properly tested? Were the most relevant parts covered by automated testing?
- Code: Is the code easy to understand? Were complex decisions in the code justified in the documentation?

## The Domain Model

Here's an overview of the domain model of the application:

![Domain Model](./assets/domain-model.png)

Note: Feel free to adapt the model in case you feel it can be improved.

### Models attributes

**Culture Type**

- id: integer
- name: string, required

**Applicant**

- id: integer
- first_name: string, required
- last_name: string, required
- culture_type: string (default: `undefined`, one of "culture_types")

**Company**

- id: integer
- name: string, required
- culture_type: string (default: `undefined`, one of "culture_types")

**Match**

- id: integer
- applicant_id: foreign key to Applicant
- company_id: foreign key to Company

## The Backend API

## General requirements

- Timestamps, when presented, should be presented in in ISO8601 format.
- API architecture: REST.
- API documentation: OpenAPI.
- Database: PostgreSQL.
- Your solution should be properly tested (all tests should be passing).
- Your solution should be properly documented (we should be able to run it based on your instructions without any issues).
- Your solution should be linted (We recommend using Rubocop for that).

### Specific Requirements

***Preferred:***

- Framework: Ruby on Rails (API)
- Language: Ruby

In case you are not familiar with Ruby on Rails, you can write the backend API in your language/framework of choice, as long as the general requirements as observed.

## Extra mile (optional)

- A dockerized solution would be very much appreciated.

## Out of scope

- Any form of authentication
- Any form of data encryption

## The Web Client

## Product requirements

- It should be possible to create culture types
- It should be possible to list culture types

- It should be possible to create companies and select a culture type.
- It should be possible to create applicants and select a culture type.

- It should be possible to visualise the list of companies
- It should be possible to visualise the list of applicants

- It should be possible to match applicants and companies

- As a company, it should be possible to visualise the matched applicants

## Business rules

### Computation of matches

- Given I'm on the frontend application, when I click on "Start match", then applicants and companies with the same culture type are matched and included into the matches table.
- Given I'm on the frontend application, when I access a company, then I should see the list of matches.
### General requirements

- Your solution should be properly tested (all tests should be passing).
- Your solution should be properly documented (we should be able to run it based on your instructions without any issues).
- Your solution should be linted (We recommend using Prettier for that).
- You are free to build your own components or use a component library of your choice.
- The UI does not need to be fancy, but it needs to be functional and meet the requirements.

### Specific Requirements

- Framework: ReactJS
- Language: JS or Typscript (whatever you feel more confortable with)
- Test framework: We recommend using Jest (not mandatory, you can choose the one you're more familiar with)
