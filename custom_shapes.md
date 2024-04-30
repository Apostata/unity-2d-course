# Custom shapes

In unity you can create custom shapes in many ways. 

## 2D Shapes

### Close sprite shape

You can create a custom shape by creating a closed sprite shape. This will allow you to create a shape with **multiple sprites**. Right click in the hierarchy window and select `2d object -> sprite shape -> closed sprite shape`.

![Closed sprite shape](./assets/closed_sprite_shape.png)

#### Adding sprites to the shape
Right click in the assets window and select `create -> 2d -> sprite shape profile`.

![Sprite shape profile](./assets/sprite_shape_profile.png)

Select the sprite shape profile and in the inspector window, you can add the sprites that you want to use in the shape.\
The closed sprite shape have some maps that you can use to create the shape, this maps are:
- **Fill texture** - This map will fill the shape with the texture that you select.
- **Edge texture** - This map will fill the edge of the shape with the texture that you select.
- **Out Top Left** - This map will fill the top left corner of the shape with the texture that you select.
- **Out Top Right** - This map will fill the top right corner of the shape with the texture that you select.
- **Out Bottom Left** - This map will fill the bottom left corner of the shape with the texture that you select.
- **Out Bottom Right** - This map will fill the bottom right corner of the shape with the texture that you select.
- **Inner Top Left** - This map will fill the top left corner of the shape with the texture that you select.
- **Inner Top Right** - This map will fill the top right corner of the shape with the texture that you select.
- **Inner Bottom Left** - This map will fill the bottom left corner of the shape with the texture that you select.
- **Inner Bottom Right** - This map will fill the bottom right corner of the shape with the texture that you select.

![Sprite shape profile](./assets/sprite_shape_profile_maping.png)

#### Editing the shape

Select the closed sprite shape in the hierarchy window and in the inspector window you can edit the shape by clicking in the `Edit spline` button.\

![Editing closed sprite shape](./assets/editing_closed_sprite_shape.png)

## Editing Sprites

By selecting a sprite in the assets window, you can edit the sprite shape in many ways, like pivot point, transparency, pixels per unit, etc. Also you can edit the shape of the sprite in the sprite editor.

### Sprite editor

You can customize the shape of a sprite by using the sprite editor. To open the sprite editor, select the sprite in the assets window and click on the `Sprite Editor` button in the inspector window.

![Sprite editor](./assets/sprite_editor.png)

In the sprite editor, you can adjust the shape of the sprite by moving the vertices of the sprite. 

![Edited sprite](./assets/edited_sprite.png)


&larr; [Back to Begin](./readme.md)