# Rails Migrations

Rails migrations will allow you to create new tables and update columns in existing database.  When the rails generate a new model a migration will also be added to that migration.

```
class CreateSignups < ActiveRecord::Migration[7.0]
	def change
		create_table :users do |t|
			t.string :email
			t.timestamps
		end
	end
end
```

When migration is generate timestamp is inputted automatically by rails.  Run the command 
bundle exec rake db:migrate to run the migration

