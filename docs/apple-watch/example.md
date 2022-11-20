
## Step by step example : Create Actions from scenes
### 1) Create a scene to close 2 covers and set light to on and another one with open covers and lights to off
- Save your existing scenes.yml (cp scenes.yml scenes.old)
- add in scenes.yml the following
```yaml
- id: '1234567890123' # any not used previously id
  name: 'Close covers and set light to ON' # scene name
  entities: # All entities affected by this scene and needed status
    light.parents: # name of an existing entity (light) in Home Assistant
      brightness: 255 # max brightness power
      state: 'on' # in this scene light must be ON
    cover.big_parents: # name of an existing entity (cover) in Home Assistant
      friendly_name: Big Cover Parent bedroom
      state: closed
    cover.small_parents: # name of an existing entity (cover) in Home Assistant
      friendly_name: Samll Cover Parent bedroom
      state: closed
- id: '1234567890123' # any not used previously id
  name: 'Open covers and set light to OFF' # scene name
  entities: # All entities affected by this scene and needed status
    light.parents: # name of an existing entity (light) in Home Assistant
      brightness: 255 # max brightness power
      state: 'off' # in this scene light must be OFF
    cover.big_parents: # name of an existing entity (cover) in Home Assistant
      friendly_name: Big Cover Parent bedroom
      state: open
    cover.small_parents: # name of an existing entity (cover) in Home Assistant
      friendly_name: Samll Cover Parent bedroom
      state: open
```
- Check the configuration files are still OK in Developers tools / YAML / Check Configuration (in v2022 in previous version it could be on Settings)
- Update the scenes configuration according to changed file
- Check the scenes appears in Settings / Automation and Scenes / Scenes 
