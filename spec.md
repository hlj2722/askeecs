##Layout of Question object

    {
		"ID":"somehexvalue",
		"Title":"A fun question",
		"Author":"Jeromy",
		"Tags":["C","Meta","Fail"],
		"Upvotes":["HexUserID"],
		"Downvotes":["AnotherHexUserID"],
		"Timestamp":"12/14/14",
		"LastEdit":"12/15/14",
		"Body":"I dont know how to program, pls help",
		"Responses": [
			{
				"ID":"tltd",
				"Author":"TravisLane",
				"Timestamp":"12/15/14",
				"Body":"Noob, go to class more.",
				"Comments":[]
			}
		],
		"Comments": [
			{
				"ID":"HexUserID",
				"Timestamp":"12/12/12",
				"Author":"JeromyJ",
				"Body":"Why is this even a question?"
			}
		]
	}

##API Layout

- Get "/q", - Get a number of questions
- Post "/q", - Ask a question [Requires Auth]

	{
		"Title":"Your questions title",
		"Body":"Your question"
	}

- Get "/q/:id", - Get Specific question
- Post "/q/:id", - Update/Edit question
- Put "/q/:id", - Delete question

- Get "/q/:id/vote/:opt", - Vote up or down on the given question

- Post "/q/:id/response", - Respond the the Specified question
- Post "/q/{id}/response/{rid}", - Update Response
- Put "/q/{id}/response/{rid}", - Delete Response

- Post "/q/:id/response/:resp/comment", - Comment on the specified response
- Post "/q/:id/comment", - Comment on the specified question
	{
		"Body":"Your comment"
	}
- Post "/q/{id}/comment/{cid}", - Update question comment
- Put "/q/{id}/comment/{cid}", - Delete question comment

- Get "/salt", - Gets a login salt for a specified user

	{
		"Username":"YourUsername"
	}

- Post "/login", - Handles a users login
- Post "/register", - Handles Registration
- Post "/logout" - Delete current user session
- Post "/me", - Get user information
