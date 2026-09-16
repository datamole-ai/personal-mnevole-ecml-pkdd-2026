`<name>` presented a semi-supervised wheelchair accessibility navigation project: crowdsourced phone-sensor data classifies sidewalk surfaces to route wheelchair users around barriers. Q&A covered sampling rates, suspension effects, and rationale for using phones over dedicated IMUs.

### Problem & Motivation
- Accessibility regulations often unenforced; temporary barriers (snow, stairs, broken/cobbled sidewalks) block wheelchair routes
- Google/Apple/OSM route pedestrians and cars, not wheelchairs
- Interviewed 17 users; needs vary by wheelchair type, environment, and user

### Approach & Dataset
- Phones mounted on multiple wheelchair locations; 183 hours, 52+ videos from US, Germany, Austria, Vietnam
- Pre-processing: filtering, resampling across phone models, normalization; merged into 7 common surface classes
- Semi-supervised clustering (mixed labeled/unlabeled) with transformer encoder; combined reconstruction + cluster loss
- Surface encoder separates surfaces better than existing sensor-data baselines; app live in Ohio, Wisconsin, Madison

### Q&A
- Sampling 100–250 Hz; cheap commercial IMUs at ~10 Hz likely too low, but slow wheelchairs tolerate lower rates
- Suspension differences across wheelchairs affect vibration patterns; only basic normalization handles it today
- Phones chosen over central IMU to enable crowdsourced data collection via a downloadable app

### Next Steps
- (<@speaker:1>) Expand app coverage beyond Ohio, Wisconsin, Madison toward global availability
- (<@speaker:1>) Continue collaboration on faster sensor-equipped collection platform to replace slow manual wheelchair runs