# Rails Controller

Index action

```
def index
end
```

New action

This is for a route that will allow users to create a new record, usually has a form

```
def new
	@user = User.new
end
```


Create action

This will create a new record in the database

```
def create
	@user = User.new(user_params)
	
	if @user.save
		redirect_to url
	else
		render :new
	end
end

private
def user_params
	params.require(:user).permit(:email)
end	
```


With the controller there might be a need for the following line

```
skip_before_action :verify_authenticity_token
```

This is a callback method telling the controller to skip the action verify authenticity token for incoming request

