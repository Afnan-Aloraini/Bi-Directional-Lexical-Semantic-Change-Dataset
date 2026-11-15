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
📘### Overview of Target Words and Semantic Change Labels (BD-LSC)

| # | Word | All Standard Meanings | All Slang Meanings | T1–T2 Label | T1–T3 Label | T2–T3 Label |
|:-:|:------|:----------------------|:-------------------|:-------------|:-------------|:-------------|
| 1 | abc | First three letters of the alphabet; basic concept | American Born Chinese; Australian-born Chinese; American Broadcasting Company | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 2 | artichoke | A vegetable; edible plant | Oral sex using teeth; vagina; an old woman; a man; “to smoke” slang | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 3 | atm | Automated Teller Machine | “At the moment”; “Ass to mouth” (porn slang) | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 4 | bam | Sudden loud noise | Scottish slang “Below Average Mentality”; interjection “Bam!”; to have sex | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 5 | battery | Device storing electricity | Jamaican slang for group sex; man using performance drugs; legal “battery” (assault) | ⚪ Stable | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss |
| 6 | beetle | An insect | A flashy young woman; to hurry away; a Volkswagen car | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 7 | bing | Heap of ore; search engine | A dose of drugs; solitary confinement cell; money | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 8 | blender | Kitchen appliance | Fingering motion during sex; euphemism for sex; aggressive person | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 9 | bmw | German luxury car brand | Derogatory reference to Black individuals (“Black Man Working”, “Black Magic Woman”); “Be My Wife” (suggestive invitation) | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 10 | bot | Robot; automatic program | Incompetent gamer; online AI; person with no individuality; “the buttocks” | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 11 | bouncer | Doorman; security guard | On-off partner; liar; large object | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 12 | breather | Brief pause; vent for air | Smoker in online meetings (“loud breather”) | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 13 | brownie | Chocolate-baked dessert; personal name or nickname; collocate in set expressions | Person who behaves foolishly; racial insult for people with brown skin; marijuana edible; vulgar reference to the anus; unit of social credit (“brownie points”) | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 14 | bush | Shrub; wilderness | Pubic hair; unsophisticated or rural person; to mug or ambush | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 15 | cheese | Dairy food | Money; marijuana; fake smile; nonsense; “the best”; bodily fluids | 🟢 Gain | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss |
| 16 | cheesy | Tasting of cheese | Sentimental, corny; cheap or fake; slang for marijuana | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 17 | chronic | Long-lasting medical condition; name of something (album, song) | Very high-quality weed; excellent; person with a particularly bad habit (negative) | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 18 | chump | Gullible person | Common worker; unsophisticated person | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 19 | climber | Person who climbs as a sport; plant that grows upward on supports | Social climber; burglar who enters buildings by climbing | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 20 | clip | Device for holding items | “Clip” a joint (weed + tobacco); to rob or kill; bundle of crack vials | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 21 | cook | To prepare food | To make meth; to falsify; to kill; to perform exceptionally | 🟢 Gain | 🟢 Gain | 🟢/🔴 Gain/Loss |
| 22 | cooker | Appliance for cooking | Meth manufacturer; sexy person; euphemism for “high” | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 23 | cool | Slightly cold; calm | Fashionable; trustworthy; “to die”; “to kill” | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 24 | cooler | Insulated container | Prison cell; drug-laced cigarette; “more cool” | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 25 | coon | Raccoon | Racial slur; sly person; goth makeup | 🔴 Loss | ⚪ Stable | 🟢 Gain |
| 26 | cosmo | Relating to the world/universe; a magazine; male given name | PCP (drug); fashionable/trendy | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 27 | crush | To squeeze; to destroy | Romantic attraction; soft drink; celebrity obsession | 🟢 Gain | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss |
| 28 | cucumber | Long green vegetable; proper noun (companies, brands, software) | Penis | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 29 | dinosaur | Prehistoric reptile | Outdated person; heroin injection slang | ⚪ Stable | 🟢 Gain | 🟢 Gain |
| 30 | douche | Cleaning product | Foolish or arrogant person | 🟢 Gain | 🟢 Gain | 🔴 Loss |
| 31 | drag | To pull; theatrical clothing | Smoking; boring event; drag queen culture; public criticism | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 32 | eat | To consume food or any substance | To perform oral sex on a woman; to make money or absorb a financial loss; to rob someone in the street; to defeat, overwhelm or destroy; to irritate or annoy | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 33 | epic | Heroic poem | Remarkable; extreme; amazing | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 34 | fan | Enthusiast; mechanical device | “Fan out” = pickpocket; to search; to calm down | 🔴 Loss | 🔴 Loss | ⚪ Stable |
| 35 | femme | Woman | Feminine partner in LGBTQ+ context | 🔴 Loss | ⚪ Stable | 🟢 Gain |
| 36 | fig | Fruit | Genitals; derogatory slur; counterfeit coin; pickpocket | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 37 | flutter | Quick wing movement | Gamble; sexual adventure; gay man | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 38 | foam | Bubbles; froth | Beer; gamer anger slang (“foam”) | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 39 | frog | Amphibian | French person; condom; to cheat | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 40 | garnish | Decorate food; legal: seize money via third party | An unlikeable hanger-on; add bling to an outfit; prison “garnish” fee; fetters; bribe | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 41 | gash | A deep cut | Vagina; rubbish/useless (mil. slang); any woman; mouth; second helping; effeminate gay man; marijuana | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 42 | gasoline | Petroleum; fuel | Vodka + energy drink; hostile/aggro (slang) | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 43 | gay | Cheerful; bright | Homosexual person; flamboyant; “stupid” (teen slang) | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 44 | germ | Microorganism that causes disease; proper noun (companies, brands); collocate in compound expressions | Cigarette (in institutional settings); derogatory term for people of German background; contemptible or unpleasant person | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢 Gain |
| 45 | ghost | Spirit | To cut off contact; to leave secretly; to murder | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 46 | gook | — | Thick viscous matter; street-walker; dull/foolish person | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 47 | gosh | Euphemism for “God” | Mild expression of surprise | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 48 | grab | Seize; clutch device | Buy/steal; arrest; have sex; “grab” attention; comprehend | 🔴 Loss | 🔴 Loss | 🟢 Gain |
| 49 | grade | Academic mark | Cannabis; money; “hot/fit” | 🟢/🔴 Gain/Loss | ⚪ Stable | 🟢/🔴 Gain/Loss |
| 50 | grit | Courage; small hard particles | Cigarette/cocaine; “gross”; a white southerner; restaurant (“gritting place”); stop talking to inmate | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 51 | hag | Witch or sorceress | Promiscuous young woman; woman with gay male best friend; hagfish | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 52 | hamburger | Ground-beef sandwich | Euphemistic expletive; “snack” (attractive person); stupid person | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 53 | harp | Musical instrument | To talk tediously (“harp on”); Irish person in US; coin tail (“harp”) | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 54 | hickey | Unnamed gadget/object; bruise | Country person; penis; rural/unsophisticated | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢 Gain |
| 55 | hike | Long walk/journey | Raise/increase; steal/trick; arrest; go away; a punch | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 56 | hive | Beehive; busy place | Vagina | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 57 | huff | Bad temper | Inhale chemicals to get high; low-grade/crappy; bully/annoy | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 58 | hun | — | Honey (term of endearment); derog. for German/Protestant in NI | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 59 | hut | Crude dwelling; shack | Someone’s open-house hangout; “over/finished”; a cell | ⚪ Stable | 🔴 Loss | 🔴 Loss |
| 60 | mammy | Colloquial or dialectal term for “mother”; proper noun (brand, company, artistic title) | Stereotypical depiction of a Black woman employed as a nanny or cook; “a large amount” | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 61 | moose | Animal | Large person; unattractive woman; close friend | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 62 | mosquito | Biting insect | Cocaine; “mosquito” as a pesty person | 🔴 Loss | ⚪ Stable | 🟢 Gain |
| 63 | mug | Cup; face; to rob | Fool; victim; face; to trick; to kiss | 🟢/🔴 Gain/Loss | 🟢 Gain | 🟢/🔴 Gain/Loss |
| 64 | penguin | Flightless bird | Soulmate; nun; LSD drug | 🔴 Loss | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss |
| 65 | pitch | To throw; a sports field; the highness or lowness of a sound; a dark sticky tar | Persuasive sales talk; a street seller's spot; to tell a tale or speak persuasively; to pass counterfeit money | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 66 | player | Game participant | Womanizer; manipulator; dealer | 🟢 Gain | 🟢 Gain | ⚪ Stable |
| 67 | posse | Legal group | Crew; gang; one’s circle of friends | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 68 | psych | Psychology | To trick; to mentally prepare; to intimidate | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 69 | putty | Linseed compound; polishing powder | Vagina; easily influenced person; money; poor-quality hash | 🔴 Loss | 🟢 Gain | 🟢 Gain |
| 70 | quaker | Member of Religious Society of Friends; duck making a “quack” | Extremely dim person; a hard/long stool | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 71 | rad | Radiation dose unit | Intensifier: excellent/extreme/very | 🟢 Gain | 🟢 Gain | 🔴 Loss |
| 72 | ratchet | Tool mechanism | Unrefined woman; wild behavior; pistol | 🟢 Gain | 🟢 Gain | 🟢 Gain |
| 73 | riff | Short repeated musical phrase | Personal style or variation; a joke or line; an argument; a rumour; to chatter, boast, complain or offend | 🟢 Gain | 🟢 Gain | 🟢/🔴 Gain/Loss |
| 74 | rodent | Mammal of the order Rodentia (rats, mice, hamsters, squirrels) | Insult for an unattractive, untrustworthy or unintelligent person | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 75 | salty | Containing salt or tasting salty; proper noun (animals, brands, songs) | Irritated, annoyed or resentful; old, worn or well-used; tough, aggressive or hardened; crude, obscene or vulgar | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 76 | scum | Layer of dirt | Worthless person; semen | ⚪ Stable | ⚪ Stable | ⚪ Stable |
| 77 | sketch | Rough or unfinished drawing or draft; short comedy scene | Odd or ridiculous person; methamphetamine; risky or dangerous; the rules or situation; to slash with a knife | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss |
| 78 | skinny | Very thin; tight-fitting (clothing); made with skimmed milk (coffee) | Confidential information; the truth; a street person of questionable character; a dime; a nude swim | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss | 🟢/🔴 Gain/Loss |
| 79 | spring | Season after winter; to leap or jump; a coiled metal device; a source of water | To release or escape from prison; to pay for something (“spring for”); to produce or reveal suddenly | 🟢 Gain | 🟢 Gain | 🟢 Gain |

### 📄 Citation


## 🔖 License

Our original contributions are licensed under CC BY 4.0 (see [LICENSE](LICENSE)): the semantic change labels, the sense inventory as worded by the authors, the instance identifiers, and the released Tweet IDs.

Third-party content is excluded from this licence:

- **T1 and T2 (CCOHA):** the `text` column is released in lemmatised, randomised form only, following SemEval-2020 Task 1; the underlying corpus remains subject to the COHA terms of use (Davies, 2012).
- **T3 (Twitter):** tweet texts are not redistributed; only Tweet IDs are released, for retrieval via the authorised X API under its developer terms.
- **Dictionaries:** no verbatim dictionary entries or definitions are redistributed; these sources remain subject to their respective copyright.

---


