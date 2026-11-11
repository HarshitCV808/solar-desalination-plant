# Solar-powered desalination plant

A simple 3D model of a small plant that turns salt water into fresh water using solar power, and a presentation based on it.

## Files

- `index.html`: the interactive 3D model. Open it in a browser (it needs an internet connection to load the three.js library). Drag to rotate, scroll to zoom, click a part or use **Next part** to step through the process.
- `Solar-Desalination-Plant.pptx`: 11-slide deck with speaker notes on every slide.
- `images/`: pictures of the model used in the deck. Add `?shot=overview` (or `intake`, `power`, `ro`, `outputs`, `plain`) to the model's address to get the same fixed views.

## The process

| Label | Part | Job |
|---|---|---|
| A | Solar panels | Turn sunlight into electricity |
| B | Battery and charge controller | Store energy so the pump runs steadily |
| 1 | Salt-water beaker | Stands in for the sea: 35 g of salt per litre |
| 2 | Pre-filters | Remove sand and silt that would clog the membrane |
| 3 | High-pressure pump | Raises the salt water to about 55 bar |
| 4 | Reverse-osmosis membrane | Lets water through, holds at least 99% of salt back |
| 5 | Brine container | Collects the salty reject, apart from the feed |
| 6 | Mineral filter | Adds calcium and magnesium |
| 7 | UV disinfection | Kills germs (drinking line only) |
| 8 | Drinking-water tank and tap | Closed, food-safe storage |
| 9 | Irrigation tank | Stores water for plants |

## Numbers: what is sourced and what is assumed

All performance figures are **design estimates**. Nothing has been built or measured.

Assumptions (set in the `D` block at the top of the script in `index.html`; the page checks that water, salt and energy balance):

- 20 L of fresh water a day: 12 L drinking (4 people at 3 L), 8 L irrigation
- Recovery 10% (1 L fresh per 10 L salt water), so 200 L in and 180 L of brine
- Membrane holds back 99% of salt, giving 350 mg/L in the fresh water
- 100 W panel, 5 peak sun hours, 70% system efficiency, giving 350 Wh a day
- Pump energy 8.5 Wh per litre, giving 170 Wh a day (UV lamp not counted)

Sources:

- Ocean share of Earth's water, 96.5%: USGS Water Science School, <https://www.usgs.gov/water-science-school/science/how-much-water-there-earth>
- 2.2 billion people without safely managed drinking water (2022 data): WHO/UNICEF Joint Monitoring Programme
- Drinking water palatable under 600 mg/L dissolved solids: WHO guidance as quoted by NHMRC, <https://guidelines.nhmrc.gov.au/australian-drinking-water-guidelines/part-5/physical-chemical-characteristics/total-dissolved-solids>
- Irrigation water, no restriction under 450 mg/L salts and 0.7 mg/L boron: FAO Irrigation and Drainage Paper 29, Table 1, <https://www.fao.org/4/t0234e/T0234E01.htm>
- Desalinated water without magnesium harmed crops: Yermiyahu et al., *Science* 318 (2007), "Rethinking desalinated water quality and agriculture"
- Small 12 V desalinator (4 A, about 5.7 L/h, 8.5 Wh per litre, 98.4% average salt rejection): Katadyn PowerSurvivor 40E, <https://www.katadyngroup.com/us/en/item~p6702>
- Osmotic pressure of sea water about 27 bar, operating pressure 55 bar and up: Open University, "The reverse osmosis (RO) process", <https://www.open.edu/openlearncreate/mod/page/view.php?id=161929>

## Known limits

- The reference unit's 98.4% salt rejection would give about 560 mg/L: drinkable, but above the FAO no-restriction level for irrigation. The design therefore requires a 99% membrane.
- Boron removal is not modelled. Membranes remove boron less well than salt, so it must be measured on a real unit.
- Membrane cleaning, fouling and pump start-up are not modelled.
- Water from any real unit must be lab-tested before anyone drinks it.
