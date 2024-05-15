# Sprites

Sprites are 2D graphic objects used for characters, props, projectiles, and other elments in a game. They are used in 2D games to represent characters, props, projectiles, and other game objects. In Unity, you can create a sprite by importing an image file into your project and then using it in a scene. You can also create a sprite by using the Sprite Editor.

## Creating a Sprite

To create a sprite, you can import an image file into your project. To do this, right click in the assets window and select `import new asset`. Then select the image file that you want to import.

## Editing Sprites

By selecting a sprite in the assets window, you can edit the sprite shape in many ways, like pivot point, transparency, pixels per unit, etc. Also you can edit the shape of the sprite in the sprite editor.

### Sprite editor

You can customize the shape of a sprite by using the sprite editor. To open the sprite editor, select the sprite in the assets window and click on the `Sprite Editor` button in the inspector window.

![Sprite editor](./assets/sprite_editor.png)

In the sprite editor, you can adjust the shape of the sprite by moving the vertices of the sprite. 

![Edited sprite](./assets/edited_sprite.png)

## Warning - Image Without Border

If you see an warning `image without border`, 

![Error image](./assets/image_without_border.png)

it means that the sprite is not set up correctly. To fix this, you can adjust the sprite borders in the sprite editor. 
After you adjust the sprite borders, the warning will disappear.

![Sprite editor](./assets/sprite_editor2.png)
