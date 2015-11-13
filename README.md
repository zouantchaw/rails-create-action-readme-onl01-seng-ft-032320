# Create Action

## Objectives

1. Use the console to create and persist an AR instance
2. Build a functional create action that can use form data in params to persist a corresponding AR instance
3. Instantiate an empty instance of a model in create
4. Manually assign data to an instance from params
5. Save an instance of AR in a controller action
6. Understand the missing template error in a create action
7. Use redirect_to to redirect in a controller using a route helper (redirect_to post_path(@post))

## Notes

Given a posts#new and a form.html.erb pointing to posts#create and passing data, how do we actually make a post and persist to our database.

we know from console, we can most a post with Post.new and then setting attributes and saving it.

Let's copy that code to posts#create.

Instead of having hard coded data, where is our form data located? params.

Let's use params to manualy assign the post data from the form to the instance of the post and save it.

After we save it, lets submit the form and use the console to see if the post was created.

it was.

but we got a rails error. why? because at the end of the posts#create, we left no instructions and rails default took over and tried rendering create.html.erb. What do we want to happen at the end of a create? let's redirect to posts#show for that post

redirect_to helper method in a controller.

lets use post_path(@post) to redirect to the newly created post. And we're all good.
