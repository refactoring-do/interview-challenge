<p>
  <a href="https://refactoring.do" target="blank"><img src="https://refactoring.do/assets/svg/refactoring-logo-full.svg" width="300" alt="Refactoring's Logo" /></a>
</p>

# Frontend take-home exercise

## What to expect?

We understand that your time is valuable, and in anyone's busy schedule solving these exercises may constitute a fairly substantial chunk of time, so we really appreciate any effort you put in to helping us build a solid team.

## What we are looking for?

Keep it simple. Read the requirements and restrictions carefully and focus on solving the problem.

Treat it like production code. That is, develop your software in the same way that you would for any code that is intended to be deployed to production. These may be toy exercises, but we really would like to get an idea of how you build code on a day-to-day basis.

### What we evaluate in the code

- Modularity
- Code organization
- Exception handling and logging
- Writing and organizing tests
- Asynchronous programming
- Components and Minimalism

## How to submit?

You can do this however you see fit - you can email us a link to download your code from somewhere or just a link to a source control repository. Make sure your submission includes a small README, documenting any assumptions, simplifications and/or choices you made, as well as a short description of how to run the code and/or tests.

## The Interview

After you submit your code, we will contact you to discuss your solution. The interview will cover a wide range of technical and social aspects relevant to working at Refactoring, we will also take the opportunity to step through your submitted code with you.

# Let's get started

Let's pretend we launched the new Job Portal for developers. Your objective as a frontend developer is to create a minimalism portal to filter IT job offers by tags.

## Development Requirements

### Which technologies can you use?

- **JavaScript Framework** (choose one):
    - React.js
    - Vue.js
    - Angular
    - Svelte
- **Software Principles**: SOLID, Clean Code.
- **Version control**: Git + GitHub

### Nice to have (not required)

- Use Typescript
- Use an strategy to paginate the API results
- Dockerize and deploy your application using GitHub Actions
- Deploy the web application to the cloud (choose one):
    - Microsoft Azure
    - AWS
    - Google Cloud Platform


### Derivables

1. **Consume the service**: get the latest remote job offers from the official [Remotive.io API](https://remotive.io/api/remote-jobs?limit=150).
2. **Integration**: build a web interface to display the job offers.
3. **Filtering**: create a filter strategy based on jobs offers tags.

### Mockup

You can be as creative as you want in the web application design. Some examples are shared below for inspiration:

 1. Job offers list
    - ![alt Job offers list](https://i.imgur.com/Mb4jHOy.png)

 2. Job offers filter based on tags
    - ![alt Job offers filter](https://i.imgur.com/6cYKtc1.png)

## API Documentation

This API returns the list of all **active** remote job listings on Remotive job board.
Filtering is available using optional querystring parameters as described below.
Remote job listings are sorted by publication date on Remotive job board.

### URL endpoint for HTTP Request

> GET [https://remotive.io/api/remote-jobs](https://remotive.io/api/remote-jobs)

### Optional Querystring Parameters

Following **optional** querystring parameters can be used to filter job listings.

| Parameter | Description | Example
| ------ | ------ | ------ |
| category | Retrieve jobs only for this category. Category name or category slug must be provided here. Existing categories are available at [this endoint](https://remotive.io/api/remote-jobs/categories). | <https://remotive.io/api/remote-jobs?category=software-dev>
| company_name | Filter by company name. Case insensitive, partial match ('ilike') will be used here to filter job listings based on provided company name. | <https://remotive.io/api/remote-jobs?company_name=remotive>
| search | Search job listing title and description. Case insensitive, partial match ('ilike') will be used here to filter job listings. | <https://remotive.io/api/remote-jobs?search=front%20end>
| limit | Limit the number of job listing results (default: all). An integer must be provided. | <https://remotive.io/api/remote-jobs?limit=5>

### Response

For example, the following request:
> curl 'https://remotive.io/api/remote-jobs?limit=1'

Would return a JSON response with the following format:

```json
{
    "0-legal-notice": "Remotive API Legal Notice",
    "job-count": 1, # Number or jobs matching the query == length of 'jobs'list
    "jobs": # The list of all jobs retrieved.
    [
        # Then for each job, you get:
        {
            # Unique Remotive ID
            "id": 123, 
            # Job listing detail url
            "url": "https://remotive.io/remote-jobs/product/lead-developer-123", 
            # Job title
            "title": "Lead Developer", 
            # Name of the company which is hiring
            "company_name": "Remotive", 
            # URL to the company logo
            "company_logo": "https://remotive.io/job/123/logo", 
             # See https: # https://remotive.io/api/remote-jobs/categories for existing categories
            "category": "Software Development",
            # full_time/contract/part_time/freelance/internship here.It 's optional and often not filled.
            "job_type": "full_time", 
            # Publication date and time on remotive.io
            "publication_date": "2020-02-15T10:23:26",
            # Geographical restriction for the remote candidate, if any.
            "candidate_required_location": "Worldwide", 
            # salary description, usually a yearly salary range, in USD. Optional.
            "salary": "$40,000 - $50,000", 
            # HTML full description of the job listing
            "description": "The full HTML job description here", 
        },
    ]
}
```

## FAQ

**Is it OK to share your solutions publicly?** Yes, the questions are not prescriptive, the process and discussion around the code is the valuable part. You do the work, you own the code. Given we are asking you to give up your time, it is entirely reasonable for you to keep and use your solution as you see fit.

**Should I do X?** For any value of X, it is up to you, we intentionally leave the problem a little open-ended and will leave it up to you to provide us with what you see as important. Just remember to keep it simple. If it's a feature that is going to take you a couple of days, it's not essential.

**Something is ambiguous, and I don't know what to do?** The first thing is: don't get stuck. We really don't want to trip you up intentionally, we are just attempting to see how you approach problems. That said, there are intentional ambiguities in the specifications, mainly to see how you fill in those gaps, and how you make design choices. If you really feel stuck, our first preference is for you to make a decision and document it with your submission - in this case there is really no wrong answer. If you feel it is not possible to do this, just send us an email and we will try to clarify or correct the question for you.

Good luck!
