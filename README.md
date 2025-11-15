# GAME_PROGRAM-EX--5

## Making Player to collect the ammo and increase the bullet spawn count.

Aim
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

## Procedure
#### 1. Setup Player Character
   1.Open your PlayerCharacter Blueprint.s

   2.Add a new Integer variable named AmmoCount.
  
   3.Set an initial default value (e.g., AmmoCount = 10).
  
   4.Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.
#### 2. Create Ammo Pickup Blueprint

 1.Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup.

 2.Add components:
  
  3.Static Mesh: Representing the ammo (e.g., a bullet or crate).

4.Sphere Collision: To detect overlap with the player.

5.In the Event Graph of BP_AmmoPickup:

6.Use OnComponentBeginOverlap on the Sphere Collision.

7.Cast to PlayerCharacter.

8.Increase the player’s AmmoCount (e.g., AmmoCount += 5).

9.Optionally, play a pickup sound or effect.

10.Destroy the ammo pickup actor.
#### 3. Update Shooting Logic (Optional)

1.In your player’s shooting logic:

2.Before spawning a bullet, check if AmmoCount > 0.

3.If true:

4.Spawn bullet.

5.Decrease AmmoCount by 1.
#### 4. Place Ammo in the World

1.Drag instances of BP_AmmoPickup into your level from the Content Browser.

2.Adjust position, mesh, and pickup range as needed.

### Output

<img width="1918" height="856" alt="image" src="https://github.com/user-attachments/assets/130a224f-89f2-416c-a21b-ad71c6089c0e" />
<img width="1335" height="839" alt="image" src="https://github.com/user-attachments/assets/55f1d4ff-25f5-45ab-bf33-6088ed35002a" />
<img width="1919" height="1013" alt="image" src="https://github.com/user-attachments/assets/e3e16845-04ea-4306-9b14-12731bc8445e" />
<img width="1134" height="765" alt="image" src="https://github.com/user-attachments/assets/c09b6e7c-1f93-4067-8cf9-638f62ad26cb" />

### Result
1.The player starts with a limited number of bullets.

2.When the player overlaps with an ammo pickup:

3.The ammo is collected.

4.The player's AmmoCount increases.

5.The player can now fire additional bullets based on the updated ammo count.
