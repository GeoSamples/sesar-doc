---
description: How the location of a sample was determined.
icon: compass
---

# Location Method

Location method is a controlled list. Use it for how the location of a sample was determined — for example GPS, DVL, or LBL.

Leave it blank if you do not know how the location was determined. Use **Not Applicable** when a location method does not apply.

The web form labels this field **Navigation type / Location method** and shows a dropdown of these labels. Sample registration, batch upload, and other API writes expect the **location method label** exactly as listed below.

If a term you need is missing, [request a term](request-a-term.md).

| Location method | Description |
| --------------- | ----------- |
| ACOUSTIC_RANGING/GPS | Acoustic ranging from a GPS-navigated ship to identify the location of instrumentation on the seafloor. |
| DGPS | Differential GPS |
| DVL | Doppler Velocity Log |
| DVL/LBL | Real-time DVL dead-reckoning navigation supplemented with LBL navigation to help constrain fixes to a geographic coordinate system. Errors on the order of 10s (sometimes 100s) of meters are likely in these data. |
| DVL/LBL/INS | Real-time DVL dead-reckoning navigation supplemented with LBL navigation and INS (Inertial Navigation System) navigation. |
| DVL/LBL:Renav | Post-processed to merge DVL with LBL navigation. When combined with LBL navigation, precision depth measurements, and gyrocompass attitude data, DVL navigation can result in vehicle positioning accuracy ranging from <1 meter to 10s of meters depending on deployment geometry and conditions, and the nature of the post-processing [Kinsey and Whitcomb, 2004, 2006; Ferrini et al., 2005; Kinsey et al., 2006; Ferrini et al., 2007]. **Note that sample position information derived from this navigation product MUST be manually verified (e.g. with bottom photos) to ensure the success of navigational post-processing.** |
| DVL/LBL:Renav:Confirmed | Indicates that the DVL/LBL:Renav positions have been confirmed by human inspection. |
| DVL/USBL | Real-time DVL dead-reckoning navigation supplemented with USBL. |
| DVL/USBL:Renav | Post-processed to merge Doppler Velocity Log (DVL) with Ultra-Short BaseLine (USBL) navigation. |
| DVL:Renav | DVL data post-processed to remove obvious errors in Doppler position data. Errors on the order of 10s of meters are likely to exist in these data and are due to the limitations of dead-reckoning navigation with DVL sonars. Users should refer to bottom photos to verify positioning information. |
| DVL:Renav:Confirmed | Indicates that the DVL:Renav positions have been confirmed by human inspection. |
| GLONASS | Global Navigation Satellite System |
| GPS | Global Positioning System |
| GPS/WireOut | Ship navigated with GPS, but sampling device launched on a wire. |
| GPS:Assumed | GPS was available and has been assumed to be the source of navigational information. |
| LAYBACK | Layback navigation is typically calculated based on (1) the ships GPS coordinates, (2) the amount of wire out to the towed platform, (3) the water depth of the platform (if available). |
| LAYBACK/LBL | Layback navigation supplemented with LBL |
| LBL | Real-time Long BaseLine navigation [Hunt et al., 1974; Milne, 1983]. Utilizes travel times from acoustic transponders deployed near the seafloor to calculate positional information. Motion of the transponders, which are typically deployed on long tethers (up to 600 m in high relief terrain), result in motion of the reference frame, introducting positioning uncertainties on the order of meters. |
| Locale | Position substituted from neighboring physiographic feature or deployed instrument. |
| LORAN | LOng RAnge Navigation |
| Not Applicable | Not applicable |
| RTK GPS | Real-Time Kinematic GPS |
| USBL | Ultra-Short Baseline |
