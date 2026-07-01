# Sitewire Coding Challenge

Hi\! 👋 Thanks for considering Sitewire\! We're excited you've decided to interview with us.

For this portion of your interview, you will be **coding a simple app using the language and/or framework of your choice**. Your app will display some data from the API server located at: [https://fake-users-api.vercel.app](https://fake-users-api.vercel.app)

We don't expect you to spend more than an hour on this. You can use whatever tools you want to build it, including AI coding assistants/tools. No matter how you write the code, you should be prepared to present what you've built and explain and defend your implementation.

## The Fake Users API

At [https://fake-users-api.vercel.app](https://fake-users-api.vercel.app) , you will find a REST API server. This REST API server has some problems, including:

* **It randomly fails.** When a random failure occurs, the server responds with a 500 status code and an error message. You can expect about 25% of your requests to fail.  
* **It experiences random slow-downs.** Some responses are quite fast (\~10ms), but some responses can take up to 3s.

### API Endpoints

The API server always responds with JSON and only has two endpoints.

#### GET `/users` \-\> `User[]`

Returns a list of user profile information. Here's an example response:

```json
[
  {
    "id": 1,
    "first_name": "Orazio",
    "last_name": "Slipper",
    "email": "oslipper0@army.mil"
  },
  {
    "id": 2,
    "first_name": "Madeline",
    "last_name": "Cornbell",
    "email": "mcornbell1@mashable.com"
  }
]
```

#### Get `/users/:id/relationships/logins` \-\> `UserLogins`

Returns a list of user logins. Here's an example response:

```json
{
  "user_id": 1,
  "logins": [
    {
      "login_time": "2026-11-13T11:21:48Z",
      "ip_v4": "115.31.131.47"
    },
    {
      "login_time": "2026-12-25T07:23:24Z",
      "ip_v4": "61.129.200.209"
    },
    {
      "login_time": "2026-06-14T19:40:28Z",
      "ip_v4": "118.36.51.49"
    }
  ]
}
```

## Your Task

Your task is to use the API server to display a list of user profile information alongside the last (most recent) time the user logged in. This can be done however you want: in a CLI app, on a webpage... pick whatever you're most comfortable working with.

Specifically, you should display the following information:

* User ID  
* Full name  
* Email address  
* Last (most recent) login time  
* Last (most recent) login IP address

You should also display a total count for the number of users in your list.

**Don't focus on visual polish.** Focus on the *states* the app and its data can be in, displaying the correct information, and how your technical decisions affect the experience of using the app your build.

## Bonus Tasks

These are truly bonuses \-- don't sweat if you don't have time to implement these. But think about how you'd approach them and we can chat about it.

* Display the country associated with the user's last login IP address.  
* Display the login time using a "humanized" format (e.g. "a minute ago", "1 month ago").  
* Highlight (or otherwise call out) any users who haven't logged in for at least one month.
