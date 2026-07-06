**Critique Overview**  
Make these 4 considerations the core of your critique process:  
**1\. What is the objective of the design?**

- To convert local environmental data (ambient temp, humidity, surface temp, solar exposure) into actionable insights for arch/urban planning/plant ops, helping them identify where local heat sinks are on campus and making climate conscious decisions (at a glance).   
- E.g. where to add buildings/new additions (greenery, walking paths, etc.) on campus (urban planning students), what **kinds** of buildings to actually build (arch eng students)  
- Short-term: helping the people who build campus cope with conditions that are shifting faster and more erratically than they used to, by making visible exactly where the existing built environment is making that worse. A heat sink that would've been merely uncomfortable in 2006 is a genuinely hazardous microclimate in a summer that already runs hotter and longer than it used to. **Identifying that now, and feeding it to someone who can act on it before the next building cycle, is a real, if small, adaptation intervention: fewer heat-exposed students, safer outdoor spaces, more informed decisions about where shade and permeable surface actually need to go.**  
- Long-term: what gets locked in. A building like M4 will stand for 50-100 years. Every siting and material decision made either **compounds the campus's heat-island effect** or **reduces it for the entire lifespan of that structure**. That's not adaptation, that's **mitigation**: less impervious surface and more canopy means less reflected/re-radiated heat, which means less mechanical cooling load, which means lower operational carbon, which is the actual mechanism by which Waterloo's Shift:Neutral 2050 carbon-neutral commitment gets hit or missed.   
- Extreme heat stress frequency has doubled in North America since the 1970s, with Canada's annual extreme-heat days projected to double over the next 30 years — the hazard is measurably escalating, not static.  
- Heat alerts rely on outdoor met data that doesn't reflect the local/indoor conditions people actually experience — confirmed by a Quebec smart-thermostat study during the 2018 heat wave, directly supporting the scale mismatch argument.  
- Embodied carbon locks in immediately at construction and can't be reversed, while buildings with 50-year lifespans emit 3x more CO2 than those lasting 80 years — quantifies exactly what "locked in for the building's life" means.  
- Building materials directly drive local surface temperature: green roofs show significantly lower surface temps than conventional roofing (EPA data) — links material/orientation choice straight to heat sink formation and cooling load.  
- Waterloo's Shift:Neutral commits to 2050 carbon neutrality and explicitly targets embodied carbon plus low-carbon design standards for new buildings — direct institutional hook for why this data matters now, before the next building cycle.

Potential Issue: Urban planners and architects already know, intuitively and from existing data sources (see data sources research section), where the hot spots / heat sinks are on a campus: parking lots, south/west-facing facades, unshaded plazas, dark asphalt paths. Satellite LST data already gives city-wide surface temperature maps, and any planner walking the campus at 2pm in July can point at the obvious offenders. Using heat sink data to inform design decisions might not solve a real problem for urban planners / arch engineers

**Other potential gaps (validate in interviews):**

The things satellite data and intuition *can't* give them, that a ground sensor node can:

1. **Before/after validation of an intervention.** If a planning team adds a tree, a cool-roof coating, a shade structure, or repaves with a lighter material — did it actually work, and by how much? Focus on the continuous monitoring of urban planning decisions   
2. **Monitoring existing green infrastructure performance over time**, e.g., is a green roof or planted median actually delivering the cooling it was designed for, which almost nobody tracks after installation.  
- In super basic terms, the objective of the actual device is to measure how hot different outdoor surfaces get compared to a nearby green area, so we can find "heat sink" spots on campus (like pavement or buildings that trap and release heat) versus spots where trees or shade are already keeping things cool.   
- We're building this for Architectural Engineering and Urban Planning students, so they have real data to point to when deciding where the campus needs more trees, shade, or better building materials.

**2\. What elements of the design are related to the objective?**

- Web app/UI: translating complex data collected from hardware components into a easily exportable data and actionable insights (suggestions, translating data), comparisons, and trends   
  - Trend/time-series visualization \- identifying patterns  
  - Two-persona dashboard (arch eng \+ urban planning student)  
- Box Design: translating weather factors and also components factors to design the box. Ex: slanted vents for humidity sensor and also so rain doesn’t go in, designing for adverse weather conditions (e.g. heat in the heat wave, rain)  
- Hardware components: what sensors/firmware we need to measure the raw data at different spots on campus and how they’re effective in collecting relevant data  
  - MLX90614 surface temperature reading: identifies a currently hazardous microclimate  
  - AHT20 ambient temp/humidity: lets facilities or a planner flag a location as needing intervention this term, not in a future building cycle  
  - BH1750 solar exposure: tracked all day, allows an arch eng student to justify a shading device or a solar-chimney-style feature (e.g. M4)  
- Surface-vs-ambient differential \- the calculation that turns raw sensor data into a meaningful signal (big gap \= heat sink, small gap \= mitigation already working).

**3\. Are these elements effective in achieving the objective?**

- Hardware piece: effectively captures the raw signals needed but it does not measure the environmental impact directly (impact lives in the software)  
- Box design protects the accuracy of the readings the system depends on (indirectly effective)  
- How are we measuring the success in our design’s purpose? 

**4\. Why or why not?**

- Yes. We are measuring success by whether the dashboard clearly shows a meaningful difference (or lack of one) between the built surface and its control point, and whether that difference is easy enough for a planning or Arch Eng student to understand and act on without having to interpret raw sensor numbers themselves.   
- Success isn't just "did we collect data", it is "does the data, once processed and displayed, clearly show whether this site is a heat sink."

First 5 minutes: Explain the design, the context, and the objectives. Provide an opportunity to clarify any assumptions or questions.

- All group members discussing the design  
- Arch eng \+ urban planning vs plant ops  
- How do students consider the effects on the environment in their design process  
- Do more research 

**Research:**   
M4:

- Site history matters: the M4 site involved demolishing an old pedestrian bridge and tearing up a section of road running from Ring Road to MC/M3, along with relocating storm sewers, sanitary sewers, and water mains that ran under it — i.e., this building is literally replacing pavement (a heat sink, in your framing) with a large structure. **That's a concrete, named example of the exact kind of site-conversion decision your tool is meant to inform.** *Taylor & Francis Online*  
- M4 will be one of a limited number of Canadian buildings to feature a **solar chimney**, an architectural feature that harnesses natural forces to ventilate and cool, reducing the building's energy use. That's an arch-eng response to solar exposure and heat, exactly the kind of decision you surface-temp /solar-exposure sensor data would feed into on a future project. 

What urban planners weigh (site/campus scale)

- **Surface material and impervious cover**: urban areas run on average 10°F warmer than surrounding natural land cover because of the high concentration of buildings, roads, and other impervious surfaces that absorb and re-emit solar radiation while blocking water percolation that would otherwise support vegetation. This is the direct academic backing for your team's "heat sink" framing.   
- **Building density, layout, and green coverage**: planning indicators like building density, floor area ratio, and green coverage significantly shape the microclimate of the built environment that results, which is why planners model 3D massing before finalizing where something goes, not just what fits on a lot.   
- **Wind corridors and street-canyon effects**: the ventilation rate and heat removal from a street canyon are dominated by canyon morphology, and changing the aspect ratio of a canyon significantly changes air ventilation rate. Poor massing between buildings can trap heat or create uncomfortable wind tunnels (this directly echoes your Ring Road wind-tunnel findings from D3). arxiv  
- **Tree canopy and shade placement**: taller buildings and trees both reduce mean radiant temperature through shade casting, with increased tree shade producing a significant reduction in thermal exposure, especially on sidewalks.   
- **Material albedo trade-offs** — worth flagging as a real tension: reflective ("cool") pavements can actually reflect solar radiation onto nearby building walls, increasing surface temperatures there, so the mitigation isn't always straightforward. 

What architectural/building engineers weigh (building scale)

- **Solar orientation and passive systems**: orienting a building and choosing features (like M4's solar chimney) around the sun path to reduce mechanical heating/cooling load. This is exactly what your BH1750 solar exposure data would inform per-façade.  
- **Building envelope and material choice** — wall/roof material affects how much heat a building absorbs and re-radiates, the same surface-temperature signal your MLX90614 captures.  
- **Sky view factor and shading from neighbors** — optimizing sky view factor and vegetation together can significantly improve outdoor and indoor thermal comfort in new designs, so engineers check how a new building shades (or fails to shade) surrounding outdoor space. arxiv  
- **Local microclimate effects on energy load** — microclimate effects can influence indoor air temperature of unconditioned buildings by up to 5°C, and newer buildings are less affected due to stricter envelope and energy-system requirements — meaning older UW buildings (like the ones your D3 interviews flagged, E2, older classrooms) are exactly where microclimate data matters most.

What kinds of data do urban planners/arch eng students use to weigh the above 

**Spatial/GIS data (used by both, foundational)**

* Zoning maps, parcel boundaries, land use layers  
* Digital elevation models (DEM) for topography and drainage  
* Aerial/satellite imagery (often from providers like ESRI, Google Earth Engine, or municipal GIS portals)  
* Floodplain maps (FEMA flood zone data in the US, conservation authority maps in Canada)  
* Soil surveys (bearing capacity, drainage class)

**Climate/environmental sensor data**

* Land Surface Temperature (LST) — often pulled from satellite thermal bands (Landsat, MODIS) rather than ground sensors, because it gives city-wide coverage even though resolution is coarse (\~30m–1km)  
* NDVI (Normalized Difference Vegetation Index) — satellite-derived greenness/canopy health metric  
* Canopy cover percentage — from LiDAR or aerial imagery classification  
* Air quality — PM2.5, NO2, ozone, often from regulatory monitoring networks or increasingly low-cost sensor networks (PurpleAir, etc.)  
* Noise levels (dB) — traffic noise modeling, sometimes measured directly  
* Wind studies — CFD (computational fluid dynamics) simulations for pedestrian-level wind comfort, especially around tall buildings  
* Thermal comfort indices — UTCI (Universal Thermal Climate Index) or PMV/PPD (Predicted Mean Vote/Percentage of People Dissatisfied), which combine temperature, humidity, wind, and radiant heat into a single "comfort" score — this is the kind of composite metric your dashboard could aspire toward

**Mobility/transportation data**

* Traffic counts (vehicle and pedestrian)  
* Transit ridership data  
* Walk Score / Bike Score style walkability metrics  
* Parking utilization studies  
* Origin-destination travel pattern data (sometimes from cell phone or transit card data now)

**Demographic/socioeconomic data**

* Census data (population density, age distribution, income)  
* Housing data (vacancy rates, affordability indices, tenure)  
* Heat Vulnerability Index or similar composite indices combining social vulnerability with physical exposure

**Building performance data**

* Energy benchmarking (Energy Star Portfolio Manager, utility billing data)  
* LEED/certification scorecards  
* BIM (Building Information Modeling) data — geometry, materials, systems, often in Revit/IFC format  
* Daylighting simulations (Radiance, or built into tools like Ladybug/Honeybee for Grasshopper)  
* Embodied carbon data (EC3 database is a common reference for material carbon footprint)  
* Material spec sheets — albedo/reflectance values, thermal conductivity, R-values

**Real-time/IoT sensor data** 

* Ambient temp/humidity, surface temp, lux   
* Occupancy sensors in buildings  
* Soil moisture sensors for green infrastructure monitoring  
* Weather station data (often from a nearby airport or campus weather station used as a baseline to compare against)

SYDE361 \- Critique Worksheet 1 of 3 

**Situation of Concern:**  

*What is the context surrounding your design solution?*


- The impacts of climate change are being seen in real time \-- more frequent heat waves, unpredictable weather events, and heat sinks are more serious exposure risk now, affecting students on campus directly by building infrastructure (e.g. E7 is climate controlled and newer whereas RCH is not and has to send individuals home in extreme weather events)  
- UW is actively building with sustainability decisions in mind now \-- M4 is an example of this, being built where a pedestrian bridge and path \+ open format used to be, with new green initiatives like how it will be one of a limited number of Canadian buildings to feature a solar chimney, an architectural feature that harnesses natural forces to ventilate and cool, reducing the building's energy use \-- showing how siting and material choice made at groundbreaking compounds or reduces campus heat sink effects  
- UW has an active carbon-neutrality commitment (Shift:Neutral, target 2050\)  
- Urban planning and architecture engineering students specifically lack access to hyperlocal environmental data when doing coursework or capstone design on campus, despite being the people whose decisions would benefit most from it  
  - Research showed there’s a gap in resolution and continuity, not the existence of data. City/campus-scale heat data (e.g. satellite land surface temperature) is low-resolution (30m–1km pixels) and infrequent (1-2 passes/day). It cannot show continuous, point-specific conditions at a single bench, walkway, or facade over time.   
  - Interview w urban planning student showed there is indeed a gap with access to sensor/live data (especially for students)

**Design Element Being Critiqued:**  

*What specific part of the design are you looking to improve by receiving input/feedback? Use  images and text to communicate the element the critique should be focussed on for the session.  \* If you need more space or a different medium, feel free to expand this description. If you’re  building a physical solution, bring a physical prototype, etc..* 

- How to measure success in the design prototype?

Specifically, how we measure whether the design achieves its objective of producing actionable insight, rather than just accurate data. Right now success is implicitly defined at the hardware layer (do the sensors read correctly?) but the objective lives at the decision layer (does a planner or arch-eng student make a different, better-informed choice because of what the dashboard shows?). We need feedback on how to define and measure that gap.

- Whether one paired site (RCH \+ control) is a defensible enough comparison to draw conclusions from, or whether our claims need to be scoped more narrowly  
- **Temporal validity of the dataset.** You're building this in July and simulating multi-year data. **Worth asking: does a reviewer trust conclusions drawn from one summer month extrapolated across seasons? If the "actionable insight" is about material/shading decisions, those decisions often depend on winter behavior too (ice, snow load, freeze-thaw), not just heat. Ask whether you need to caveat the seasonal scope explicitly rather than let the multi-year simulated dataset imply more generality than it has.**

SYDE361 \- Critique Worksheet 2 of 3 

**High Level Objectives of the Design Element:**  

*What high level objectives does the element need to help achieve as part of the overall solution?*


The success metric must let us judge whether the system changes a design or siting decision 

*  i.e. whether output moves a real user from "I intuitively know it's hot here" to "I have fundable, quantified evidence for an intervention."

 It should be measurable, tied to the two personas (arch-eng at building scale, urban planning at campus scale), and distinguish system value from mere data accuracy.

- **Support real design decisions** — be specific enough that a planner could point to it and act. Isabella confirmed this: she said heat sink data would help her "plan areas to avoid" when locating new comfortability spaces, and would change her design process by flagging when a site needs "not planning so much outdoor space" or rebalancing for shade/vegetation.  
- **Fit into existing workflows rather than compete with them** — Isabella was direct that GIS is her "one stop shop," used daily, and that layering our sensor data into a GIS-style map interface would be more valuable than a standalone website. Long-term, this should shape the display objective; short-term, it means our dashboard should be simple/structured enough that it could plausibly become a GIS layer later.

**Low Level Objectives of the Design Element:**  

*What low level objectives does the element need to achieve to be an effective part of the overall  solution?* 

**Comparison between quantitative \+ intuitive data:** The dashboard must present data in a way that lets a user immediately compare a specific reading against their own intuitive estimate — not just show a number in isolation. (Isabella's interview suggests users already have a rough mental model of "hot vs. comfortable" spaces; the system should visibly sharpen that estimate, not just restate it.)

* Accurately capture surface temperature, ambient temperature, and solar exposure at both the built site and the vegetated control, reliably across a day/night cycle.  
* Calculate a clear surface-vs-ambient differential as the core output, rather than surfacing raw values — this maps directly to what Isabella already does mentally (eyeballing whether a spot is "too hot/sunny") but with a measured number behind it.  
* Track data over time, not a single snapshot — Isabella specifically said tracking over time and adding more sites would make the data more useful to her; a one-time reading wouldn't support the kind of before/after comparison she referenced (e.g., checking whether added vegetation actually cooled a space).

SYDE361 \- Critique Worksheet 3 of 3   
**\*\*\* Fill this next section out during/after the critique session, not before \*\*\***  

**Potential Ways to Improve the Design Towards the Objectives**  *In what ways could the design possibly be improved towards achieving its objectives? Capture  all the ideas, not just ones you agree with\! Take some time between receiving the critique and  deciding which ideas to adopt and reject to allow for your emotions to digest the value of each  idea honestly.*