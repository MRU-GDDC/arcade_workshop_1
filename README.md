# arcade_workshop_1

# code
	 func _on_mob_timer_timeout():
		
		 # Create a new instance of the Mob scene.
   		 var mob = mob_scene.instance()

   		 # Choose a random location on Path2D.
   		 var mob_spawn_location = get_node("MobPath/MobSpawnLocation")
   		 mob_spawn_location.offset = randi()
	
   		 # Set the mob's direction perpendicular to the path direction.
   		 var direction = mob_spawn_location.rotation + PI / 2

   		 # Set the mob's position to a random location.
   		 mob.position = mob_spawn_location.position

   		 # Add some randomness to the direction.
   		 direction += rand_range(-PI / 4, PI / 4)
   		 mob.rotation = direction

   		 # Choose the velocity for the mob.
   		 var velocity = Vector2(rand_range(150.0, 250.0), 0.0)
   		 mob.linear_velocity = velocity.rotated(direction)

   		 # Spawn the mob by adding it to the Main scene.
   		 add_child(mob)
