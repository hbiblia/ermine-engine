# acs
Actor Component Signal - Es una versión de ECS.


```C
typedef struct
{
  int type;
} ComponentModel;

void Update(Actor *self, float dt)
{
  actor_set_rotation(self, 10 * dt, 20 * dt, 30 * dt);
}

int main(int argc, char *argv[])
{
  Scene *scene = scene_new();

  Actor *cube = actor_new('cube');
  actor_add_component(cube, "model", (ComponentModel){.type = MODEL_TYPE_CUBE});
  actor_signal(cube, "update", Update);

  scene_add_child(scene, cube);
  
  scene_main(scene);
  
  return 0;
}
```
