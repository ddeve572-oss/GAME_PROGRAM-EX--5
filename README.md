# GAME_PROGRAM-EX--5

## Making Player to collect the ammo and increase the bullet spawn count.
## Aim
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

## Procedure
1. Setup Player Character
Open your PlayerCharacter Blueprint.s
Add a new Integer variable named AmmoCount.
Set an initial default value (e.g., AmmoCount = 10).
Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.
2. Create Ammo Pickup Blueprint
Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup.
Add components:
Static Mesh: Representing the ammo (e.g., a bullet or crate).
Sphere Collision: To detect overlap with the player.
In the Event Graph of BP_AmmoPickup:
Use OnComponentBeginOverlap on the Sphere Collision.
Cast to PlayerCharacter.
Increase the player’s AmmoCount (e.g., AmmoCount += 5).
Optionally, play a pickup sound or effect.
Destroy the ammo pickup actor.
3. Update Shooting Logic (Optional)
In your player’s shooting logic:
Before spawning a bullet, check if AmmoCount > 0.
If true:
Spawn bullet.
Decrease AmmoCount by 1.
4. Place Ammo in the World
Drag instances of BP_AmmoPickup into your level from the Content Browser.
Adjust position, mesh, and pickup range as needed.

## Output
<img width="1040" height="436" alt="image" src="https://github.com/user-attachments/assets/9f37b8ef-2ca7-4448-8f3b-2c375d051686" />
<img width="996" height="637" alt="image" src="https://github.com/user-attachments/assets/1dc27247-ad8e-4c37-a9b5-8f540f77000b" />
<img width="1042" height="553" alt="image" src="https://github.com/user-attachments/assets/99c13f6b-acae-4e55-9407-45486ccc8ba1" />
<img width="1049" height="616" alt="image" src="https://github.com/user-attachments/assets/67e6318b-da2b-4735-91cf-ae7790559f5c" />


## Result
The player starts with a limited number of bullets.
When the player overlaps with an ammo pickup:
The ammo is collected.
The player's AmmoCount increases.
The player can now fire additional bullets based on the updated ammo count.
