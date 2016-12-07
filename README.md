# Hyper Status Bar

A status bar for Hyper.app. More information coming soon.

- Customizable location (top or bottom of terminal)
- Supports custom font, size, and scale
- Easy extensions using a simple plugin system with minimal boilerplate
- Plugins support conditional sections, automatic per-plugin configuration

The Idea: (Not yet finished, still in progress)

Plugins are structured as folders that contain a default configuration, a collection of sections that can be conditionally rendered based on configuration, and a parent component if you choose not to opt into the section structure when building a plugin.

Sections define a react component (the view) and export the name of the property in the configuration that will determine whether or not it is displayed.

Let's say you want to build a plugin that displays CPU information. You want this plugin to be configurable such that it can show all or just some of the following statistics: current speed, average speed. To do this, you simply create a new folder called `cpu-stats` which will act as the parent folder for your plugin. You then create a child folder called `sections`. Within this folder you make two files, `current_speed.js` and `average_speed.js`.

```
export const current_speed = () => (<p>{os.getCPUSpeed + "GHz"}</p>);
```
