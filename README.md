# 🧠 BD-LSC: Bi-Directional Lexical Semantic Change
### A Dataset and Benchmark for Tracking Word Meaning Evolution in Slang and Standard English

---

## 🔍 Overview

**BD-LSC** (Bi-Directional Lexical Semantic Change) is a benchmark dataset for analyzing how word meanings **gain**, **lose**, or **remain stable** over time — across both **standard English** and **slang**.  
It introduces a **bi-directional annotation scheme**, capturing the evolution of word senses across **three time periods (T1, T2, T3)**.

Unlike traditional lexical semantic change datasets that classify only “change” vs “no change,” BD-LSC explicitly distinguishes:

- 🟢 **Sense Gain (SG)** – new meanings emerge  
- 🔴 **Sense Loss (SL)** – old meanings fade  
- ⚪ **Stable (NC)** – meanings remain unchanged  

---

### 🧩 Why BD-LSC is Significant

- 🔹 **First bi-directional model of sense evolution** — captures both *gain* and *loss* of meaning across time rather than simple “change/no-change.”  
- 🔹 **Three temporal slices (T1–T3)** — enable fine-grained tracking of gradual semantic drift across decades.  
- 🔹 **Bridges slang and standard usage** — integrates parallel evolution across formal corpora (COHA/CCOHA) and informal slang sources (Urban Dictionary, SlangSD).  
- 🔹 **Cross-domain composition** — combines literary, journalistic, and social media data for a balanced linguistic spectrum.  
- 🔹 **Explicit sense inventories** — each word has a documented set of meanings linked to time-specific labels (word → sense → temporal tag).  
- 🔹 **Multi-label tagging scheme** — supports simultaneous gain/loss tracking and sense stability marking.  
- 🔹 **High-quality human annotation** — Cohen’s κ ≈ 0.9 across time periods ensures reliability and inter-annotator consistency.  
- 🔹 **Benchmark-ready design** — directly comparable with SemEval 2020, TempoWiC, and DWUG while extending beyond their two-period limitations.  
- 🔹 **Open benchmark for LLMs** — designed to test diachronic embeddings, contextual transformers, and semantic drift detection.  
- 🔹 **Reflects real cultural change** — captures how digital communication and online culture reshape English semantics in both slang and standard registers.  

---

## 🧱 Dataset Composition

| Period | Years | Source | Description |
|:------:|:------|:--------|:-------------|
| **T1** | 1980–1999 | CCOHA / COHA | Late 20th-century formal English |
| **T2** | 2000–2009 | COHA | Early 21st-century transitional English |
| **T3** | 2010–2020 | Twitter, Urban Dictionary | Modern slang and online language |

**Data Sources:**
- **Standard English:** COHA, CCOHA, Oxford English Dictionary (OED)  
- **Slang Sources:** SlangSD, Urban Dictionary, Green’s Dictionary of Slang  
- **Annotation:** 3 expert linguists (Cohen’s κ ≈ 0.9 across periods)

---

## 💬 Target Words and Change Types

The BD-LSC dataset contains **79 target lemmas**, each annotated across **T1–T2–T3** for sense change and accompanied by examples of both **standard** and **slang** usage.

---

### 🔍 Label Legend

| Symbol | Meaning |
|:-------|:--------|
| 🟢 Gain | New sense(s) or extended usage appeared |
| 🔴 Loss | Older sense(s) declined or disappeared |
| ⚪ Stable | No significant change across the period |

---

### 📘 Overview of Target Words and Semantic Change Labels (BD-LSC)

| # | Word | All Standard Meanings | All Slang Meanings | T1–T2 Label | T1–T3 Label | T2–T3 Label |
|:-:|:------|:----------------------|:-------------------|:-------------|:-------------|:-------------|
| 1 | abc | First three letters of the alphabet; basic concept | American Born Chinese; Australian-born Chinese; American Broadcasting Company | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 2 | artichoke | A vegetable; edible plant | Oral sex using teeth; vagina; an old woman; a man; “to smoke” slang | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 3 | eat | To consume food | To give oral sex to a woman; to rob; to make money; to annoy; to destroy | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 4 | atm | Automated Teller Machine | “At the moment”; “Ass to mouth” (porn slang) | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 5 | bam | Sudden loud noise | Scottish slang “Below Average Mentality”; interjection “Bam!”; to have sex | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 6 | battery | Device storing electricity | Jamaican slang for group sex; man using performance drugs; legal “battery” (assault) | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 7 | beetle | An insect | A flashy young woman; to hurry away; a Volkswagen car | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 8 | bing | Heap of ore; search engine | A dose of drugs; solitary confinement cell; money | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 9 | blender | Kitchen appliance | Fingering motion during sex; euphemism for sex; aggressive person | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 10 | bmw | Car brand | “Black Man’s Wish”; “Be My Wife”; “Black Magic Woman” | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 11 | bom | Brother; dude; friend | Bill of materials; exclamation of joy; attractive person | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 12 | bot | Robot; automatic program | Incompetent gamer; online AI; person with no individuality; “the buttocks” | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 13 | bouncer | Doorman; security guard | On-off partner; liar; large object | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 14 | breather | Brief pause; vent for air | Smoker in online meetings (“loud breather”) | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 15 | brownie | Chocolate dessert | Edible marijuana; “airhead” person; referring to brown-skinned people | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 16 | bush | Shrub; wilderness | Pubic hair; unsophisticated or rural person; to mug or ambush | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 17 | cad | Dishonest man; scoundrel | “Computer Aided Design”; “Ctrl-Alt-Del”; “Cadillac” | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 18 | cheese | Dairy food | Money; marijuana; fake smile; nonsense; “the best”; bodily fluids | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 19 | cheesy | Tasting of cheese | Sentimental, corny; cheap or fake; slang for marijuana | 🟢 Gain | ⚪ Stable | ⚪ Stable |
| 20 | chronic | Long-lasting (medical) | High-quality cannabis; “excellent” slang | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 21 | chump | Gullible person | Common worker; unsophisticated person | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 22 | climber | Person who climbs; plant that climbs | Social climber; cat burglar | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 23 | clip | Device for holding items | “Clip” a joint (weed + tobacco); to rob or kill; bundle of crack vials | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 24 | cooker | Appliance for cooking | Meth manufacturer; sexy person; euphemism for “high” | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 25 | cook | To prepare food | To make meth; to falsify; to kill; to perform exceptionally | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 26 | cool | Slightly cold; calm | Fashionable; trustworthy; “to die”; “to kill” | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 27 | cooler | Insulated container | Prison cell; drug-laced cigarette; “more cool” | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 28 | coon | Raccoon | Racial slur; sly person; goth makeup | 🔴 Loss | ⚪ Stable | ⚪ Stable |
| 29 | crush | To squeeze; to destroy | Romantic attraction; soft drink; celebrity obsession | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 30 | cucumber | Vegetable | Penis | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 31 | dap | Fist-bump greeting | Respect, acknowledgment, self-awareness; stylish | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 32 | dew | Water droplets | Sexual fluid; slang for Mountain Dew; marijuana | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 33 | dinosaur | Prehistoric reptile | Outdated person; heroin injection slang | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 34 | dip | To lower or submerge | To leave; pickpocket; drug user; stylish | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 35 | douche | Cleaning product | Foolish or arrogant person | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 36 | drag | To pull; theatrical clothing | Smoking; boring event; drag queen culture; public criticism | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 37 | dude | Man; person | Friendly greeting; “cool person”; stoner slang | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 38 | epic | Heroic poem | Remarkable; extreme; amazing | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 39 | fan | Enthusiast; mechanical device | “Fan out” = pickpocket; to search; to calm down | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 40 | femme | Woman | Feminine partner in LGBTQ+ context | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 41 | fig | Fruit | Genitals; derogatory slur; counterfeit coin; pickpocket | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 42 | flutter | Quick wing movement | Gamble; sexual adventure; gay man | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 43 | foam | Bubbles; froth | Beer; gamer anger slang (“foam”) | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 44 | frog | Amphibian | French person; condom; to cheat | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 45 | gay | Cheerful; bright | Homosexual person; flamboyant; “stupid” (teen slang) | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 46 | ghost | Spirit | To cut off contact; to leave secretly; to murder | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 47 | gosh | Euphemism for “God” | Mild expression of surprise | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 48 | germ | Microorganism | Germ of an idea; insult; prison slang for cigarette | 🟢 Gain | ⚪ Stable | ⚪ Stable |
| 49 | mammy | Mother figure | Racial stereotype; “abundance” slang | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 50 | moose | Animal | Large person; unattractive woman; close friend | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 51 | mug | Cup; face; to rob | Fool; victim; face; to trick; to kiss | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 52 | penguin | Flightless bird | Soulmate; nun; LSD drug | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 53 | player | Game participant | Womanizer; manipulator; dealer | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 54 | posse | Legal group | Crew; gang; one’s circle of friends | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 55 | psych | Psychology | To trick; to mentally prepare; to intimidate | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 56 | ratchet | Tool mechanism | Unrefined woman; wild behavior; pistol | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 57 | salty | Tasting of salt | Angry; bitter; crude language | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 58 | scum | Layer of dirt | Worthless person; semen | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 59 | cosmo | Relating to the world/universe; a magazine; male given name | PCP (drug); fashionable/trendy | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 60 | garnish | Decorate food; legal: seize money via third party | An unlikeable hanger-on; add bling to an outfit; prison “garnish” fee; fetters; bribe | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 61 | gash | A deep cut | Vagina; rubbish/useless (mil. slang); any woman; mouth; second helping; effeminate gay man; marijuana | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 62 | gasoline | Petroleum; fuel | Vodka + energy drink; hostile/aggro (slang) | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 63 | gook | — | Thick viscous matter; street-walker; dull/foolish person | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 64 | grab | Seize; clutch device | Buy/steal; arrest; have sex; “grab” attention; comprehend | 🔴 Loss | 🔴 Loss | 🟢 Gain |
| 65 | grade | Academic mark | Cannabis; money; “hot/fit” | 🟢/🔴 Gain/Loss | ⚪ Stable | 🟢/🔴 Gain/Loss |
| 66 | grit | Courage; small hard particles | Cigarette/cocaine; “gross”; a white southerner; restaurant (“gritting place”); stop talking to inmate | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 67 | hag | Witch or sorceress | Promiscuous young woman; woman with gay male best friend; hagfish | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 68 | hamburger | Ground-beef sandwich | Euphemistic expletive; “snack” (attractive person); stupid person | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 69 | harp | Musical instrument | To talk tediously (“harp on”); Irish person in US; coin tail (“harp”) | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 70 | hickey | Unnamed gadget/object; bruise | Country person; penis; rural/unsophisticated | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 71 | hike | Long walk/journey | Raise/increase; steal/trick; arrest; go away; a punch | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 72 | hive | Beehive; busy place | Vagina | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 73 | huff | Bad temper | Inhale chemicals to get high; low-grade/crappy; bully/annoy | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 74 | hun | — | Honey (term of endearment); derog. for German/Protestant in NI | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 75 | hut | Crude dwelling; shack | Someone’s open-house hangout; “over/finished”; a cell | ⚪ Stable | 🔴 Loss | 🔴 Loss |
| 76 | mosquito | Biting insect | Cocaine; “mosquito” as a pesty person | 🔴 Loss | ⚪ Stable | 🟢 Gain |
| 77 | putty | Linseed compound; polishing powder | Vagina; easily influenced person; money; poor-quality hash | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 78 | quaker | Member of Religious Society of Friends; duck making a “quack” | Extremely dim person; a hard/long stool | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 79 | rad | Radiation dose unit | Intensifier: excellent/extreme/very | 🟢 Gain | 🟢 Gain | 🔴 Loss |

---

### 📄 Citation


If you use **BD-LSC**, please cite:

> **[ ]**   
> Available at: [GitHub Repository Link]

---


