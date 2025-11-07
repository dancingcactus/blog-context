# Blog Context 

My blog is elevendegreeseast.com. It is called technobabble and it is a place for me to share my projects and and to summarize what I have learned. 

## Writing Style

The writing style is informal and a bit nerdy, though I don't like making references to fiction. Just keep it about what the project is, lots of details about how things works and the lessons learned.

## Projects

### Greenhouse Control System

One of my projects is a greenhouse control system that controls various aspects of a greenhouse environment. The system is built primarily with Home Assistant with several custom or repurposed devices that use ESP Home for their firmware. The greenhouse grows about 150-400 flower baskets each year for sale around Mother's day. 

#### Components

The system has a few different components

- A small pc running Home Assistant
- Server add-ons to Home Assistant
  - ESPHome Builder for managing the ESP home devices
  - InfluxDB for storing long term trends
  - Grafana for doing some long term analysis
  - Cloudflared for remote access
- A number of devices running the ESP Home software.
  - Several smart plugs (Wyze Outdoor Plugs) to control various fans and serve as bluetooth proxies
  - A relay board hooked to an ESP-32 that controls the heating, cooling systems, fancs and shutters
  - A number of bluetooth LE devices (Switchbot Indoor/Outdoor Thermo-Hygrometer) to measure humidity and temperature at various locations.

#### Greenhouse Details

The greenhouse it 20 feet by 50 feet. It has an inflated poly exteriour with an insulated north wall and solid walls at the two ends The floor is gravel.

The heating system is primarily a GAHT (Ground Air Heat Transfer System) wiht a few hundred feet of tubes buried between 4-8 feet down. This is also used for cooling in the summer. It serves as a earth battery to store heat from the summer to use in the fall. It is able to overwinter some plants with very little energy input.

The cooling system is a multi-stage system. First is the GAHT systme then there are two venting fans on the east wall and shutters on the west wall that turn on one at a time. Then there is an evaporative cooler that is used and finally a misting system. They are triggered in the following order as heat rises.

    1. Gaht fan
    2. Fan 1 - with open shutters 
    3. Fan 2
    4. Evaoporative Cooler
    5. Misting System

The system does not control the watering or feeding as those are handled by off the shelf times and fertilizer injectors. 

The vent fans are also used for humidity control. When the humidity gets too high they will vent the greenhouse for a short time. 