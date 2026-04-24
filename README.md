# 🏆 World Cup 2026: The Quantified Pitch
### Cracking the Code of the First-Ever 48-Team Tournament

A hybrid **Machine Learning + Monte Carlo** simulation engine that synthesizes **49,000+ historical international matches** (1872–2026) to predict outcomes for the expanded 104-match FIFA World Cup 2026.

---

## 🚀 Key Features

| Feature | Description |
|---|---|
| **Custom Elo Engine** | K-factor weighted by match type — World Cup (60), Qualifier (40), Regional (30), Friendly (10) |
| **Host Boost** | +100 Elo points for USA, Mexico & Canada as host nations |
| **Poisson Goal Layer** | Converts Elo differentials into precise Expected Goals (xG) distributions |
| **Monte Carlo Engine** | 10,000 full-tournament simulations with tie-breaker & third-place logic |
| **ML Models** | Logistic Regression, Random Forest, XGBoost, and SVM compared & ensembled |

---

## 📂 Project Structure

```
WC 26 Predictions/
├── WC predictor.ipynb          # Main pipeline notebook (7 phases)
├── results.csv                 # 49,287 historical match results (1872–2026)
├── shootouts.csv               # Historical penalty shootout records
├── former_names.csv            # Nation name normalization map
├── simulation_results.txt      # Full simulation output (groups + knockouts)
└── README.md
```

---

## 🛠️ Getting Started

### Prerequisites
```bash
pip install pandas numpy scikit-learn xgboost scipy matplotlib seaborn
```

### Run the Prediction Pipeline
Open `WC predictor.ipynb` in Jupyter. The notebook is structured into 7 self-contained phases:

| Phase | Description |
|---|---|
| **Phase 1** | Environment setup & data ingestion |
| **Phase 2** | Data cleaning, name normalization & tournament categorization |
| **Phase 3** | Custom K-Factor Elo Rating Engine |
| **Phase 4** | ML Feature Engineering (Elo diff, form, goal ratios) |
| **Phase 5** | Model training & evaluation (LR / RF / XGBoost / SVM) |
| **Phase 6** | Poisson goal probability layer |
| **Phase 7** | Monte Carlo tournament simulation (10,000 iterations) |

---

## 🏟️ Simulation Results

> The groups below are **hardcoded** in the notebook based on the official FIFA 2026 World Cup draw. The simulation uses a hybrid Elo + Poisson + Recent Form engine to predict every match.

### Group Stage Standings

<details>
<summary><strong>Group A</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **South Korea** ✅ | 3 | 3 | 0 | 0 | 6 | 3 | +3 | **9** |
| **Mexico** ✅ | 3 | 1 | 1 | 1 | 4 | 4 | 0 | **4** |
| South Africa 🟡 | 3 | 0 | 2 | 1 | 3 | 4 | -1 | 2 |
| Czech Republic | 3 | 0 | 1 | 2 | 3 | 5 | -2 | 1 |

**Matches:** Mexico 1-1 South Africa · Mexico 1-2 South Korea · Mexico 2-1 Czech Republic · South Africa 1-2 South Korea · South Africa 1-1 Czech Republic · South Korea 2-1 Czech Republic

</details>

<details>
<summary><strong>Group B</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Switzerland** ✅ | 3 | 3 | 0 | 0 | 7 | 2 | +5 | **9** |
| **Canada** ✅ | 3 | 2 | 0 | 1 | 5 | 3 | +2 | **6** |
| Bosnia and Herzegovina | 3 | 0 | 1 | 2 | 3 | 6 | -3 | 1 |
| Qatar | 3 | 0 | 1 | 2 | 1 | 5 | -4 | 1 |

**Matches:** Canada 2-1 Bosnia and Herzegovina · Canada 2-0 Qatar · Canada 1-2 Switzerland · Bosnia and Herzegovina 1-1 Qatar · Bosnia and Herzegovina 1-3 Switzerland · Qatar 0-2 Switzerland

</details>

<details>
<summary><strong>Group C</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Morocco** ✅ | 3 | 3 | 0 | 0 | 8 | 3 | +5 | **9** |
| **Brazil** ✅ | 3 | 2 | 0 | 1 | 5 | 4 | +1 | **6** |
| Haiti 🟡 | 3 | 1 | 0 | 2 | 4 | 6 | -2 | 3 |
| Scotland | 3 | 0 | 0 | 3 | 3 | 7 | -4 | 0 |

**Matches:** Brazil 1-2 Morocco · Brazil 2-1 Haiti · Brazil 2-1 Scotland · Morocco 3-1 Haiti · Morocco 3-1 Scotland · Haiti 2-1 Scotland

</details>

<details>
<summary><strong>Group D</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Australia** ✅ | 3 | 2 | 1 | 0 | 6 | 4 | +2 | **7** |
| **Turkey** ✅ | 3 | 2 | 1 | 0 | 6 | 4 | +2 | **7** |
| United States | 3 | 0 | 1 | 2 | 3 | 5 | -2 | 1 |
| Paraguay | 3 | 0 | 1 | 2 | 3 | 5 | -2 | 1 |

**Matches:** United States 1-1 Paraguay · United States 1-2 Australia · United States 1-2 Turkey · Paraguay 1-2 Australia · Paraguay 1-2 Turkey · Australia 2-2 Turkey

</details>

<details>
<summary><strong>Group E</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Germany** ✅ | 3 | 2 | 1 | 0 | 7 | 4 | +3 | **7** |
| **Ivory Coast** ✅ | 3 | 2 | 1 | 0 | 6 | 4 | +2 | **7** |
| Ecuador | 3 | 0 | 1 | 2 | 3 | 5 | -2 | 1 |
| Curaçao | 3 | 0 | 1 | 2 | 3 | 6 | -3 | 1 |

**Matches:** Germany 3-1 Curaçao · Germany 2-2 Ivory Coast · Germany 2-1 Ecuador · Curaçao 1-2 Ivory Coast · Curaçao 1-1 Ecuador · Ivory Coast 2-1 Ecuador

</details>

<details>
<summary><strong>Group F</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Japan** ✅ | 3 | 3 | 0 | 0 | 10 | 4 | +6 | **9** |
| **Netherlands** ✅ | 3 | 2 | 0 | 1 | 9 | 5 | +4 | **6** |
| Tunisia 🟡 | 3 | 1 | 0 | 2 | 4 | 7 | -3 | 3 |
| Sweden | 3 | 0 | 0 | 3 | 3 | 10 | -7 | 0 |

**Matches:** Netherlands 2-3 Japan · Netherlands 4-1 Sweden · Netherlands 3-1 Tunisia · Japan 4-1 Sweden · Japan 3-1 Tunisia · Sweden 1-2 Tunisia

</details>

<details>
<summary><strong>Group G</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Belgium** ✅ | 3 | 3 | 0 | 0 | 7 | 3 | +4 | **9** |
| **Iran** ✅ | 3 | 1 | 1 | 1 | 4 | 4 | 0 | **4** |
| Egypt 🟡 | 3 | 0 | 2 | 1 | 3 | 4 | -1 | 2 |
| New Zealand | 3 | 0 | 1 | 2 | 3 | 6 | -3 | 1 |

**Matches:** Belgium 2-1 Egypt · Belgium 2-1 Iran · Belgium 3-1 New Zealand · Egypt 1-1 Iran · Egypt 1-1 New Zealand · Iran 2-1 New Zealand

</details>

<details>
<summary><strong>Group H</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Spain** ✅ | 3 | 3 | 0 | 0 | 9 | 3 | +6 | **9** |
| **Saudi Arabia** ✅ | 3 | 0 | 2 | 1 | 3 | 5 | -2 | **2** |
| Uruguay 🟡 | 3 | 0 | 2 | 1 | 3 | 5 | -2 | 2 |
| Cape Verde | 3 | 0 | 2 | 1 | 3 | 5 | -2 | 2 |

**Matches:** Spain 3-1 Saudi Arabia · Spain 3-1 Uruguay · Spain 3-1 Cape Verde · Saudi Arabia 1-1 Uruguay · Saudi Arabia 1-1 Cape Verde · Uruguay 1-1 Cape Verde

</details>

<details>
<summary><strong>Group I</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **France** ✅ | 3 | 3 | 0 | 0 | 9 | 5 | +4 | **9** |
| **Senegal** ✅ | 3 | 2 | 0 | 1 | 8 | 6 | +2 | **6** |
| Norway 🟡 | 3 | 1 | 0 | 2 | 6 | 7 | -1 | 3 |
| Iraq | 3 | 0 | 0 | 3 | 3 | 8 | -5 | 0 |

**Matches:** France 3-2 Senegal · France 3-1 Iraq · France 3-2 Norway · Senegal 3-1 Iraq · Senegal 3-2 Norway · Iraq 1-2 Norway

</details>

<details>
<summary><strong>Group J</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Argentina** ✅ | 3 | 3 | 0 | 0 | 9 | 5 | +4 | **9** |
| **Algeria** ✅ | 3 | 1 | 1 | 1 | 6 | 6 | 0 | **4** |
| Austria 🟡 | 3 | 0 | 2 | 1 | 6 | 7 | -1 | 2 |
| Jordan | 3 | 0 | 1 | 2 | 4 | 7 | -3 | 1 |

**Matches:** Argentina 3-2 Algeria · Argentina 3-2 Austria · Argentina 3-1 Jordan · Algeria 2-2 Austria · Algeria 2-1 Jordan · Austria 2-2 Jordan

</details>

<details>
<summary><strong>Group K</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **Portugal** ✅ | 3 | 3 | 0 | 0 | 6 | 3 | +3 | **9** |
| **Colombia** ✅ | 3 | 2 | 0 | 1 | 5 | 4 | +1 | **6** |
| DR Congo | 3 | 0 | 1 | 2 | 3 | 5 | -2 | 1 |
| Uzbekistan | 3 | 0 | 1 | 2 | 3 | 5 | -2 | 1 |

**Matches:** Portugal 2-1 DR Congo · Portugal 2-1 Uzbekistan · Portugal 2-1 Colombia · DR Congo 1-1 Uzbekistan · DR Congo 1-2 Colombia · Uzbekistan 1-2 Colombia

</details>

<details>
<summary><strong>Group L</strong></summary>

| Team | P | W | D | L | GF | GA | GD | Pts |
|---|---|---|---|---|---|---|---|---|
| **England** ✅ | 3 | 2 | 1 | 0 | 8 | 4 | +4 | **7** |
| **Croatia** ✅ | 3 | 2 | 1 | 0 | 7 | 4 | +3 | **7** |
| Panama 🟡 | 3 | 1 | 0 | 2 | 4 | 6 | -2 | 3 |
| Ghana | 3 | 0 | 0 | 3 | 3 | 8 | -5 | 0 |

**Matches:** England 2-2 Croatia · England 3-1 Ghana · England 3-1 Panama · Croatia 3-1 Ghana · Croatia 2-1 Panama · Ghana 1-2 Panama

</details>

> ✅ = Top 2 (automatic qualification) · 🟡 = Best 3rd-place (advances to R32)

### Best Third-Place Teams

| Rank | Team | Group | Pts | GD | GF | Status |
|---|---|---|---|---|---|---|
| 1 | Norway | I | 3 | -1 | 6 | ✅ Advance |
| 2 | Haiti | C | 3 | -2 | 4 | ✅ Advance |
| 3 | Panama | L | 3 | -2 | 4 | ✅ Advance |
| 4 | Tunisia | F | 3 | -3 | 4 | ✅ Advance |
| 5 | Austria | J | 2 | -1 | 6 | ✅ Advance |
| 6 | South Africa | A | 2 | -1 | 3 | ✅ Advance |
| 7 | Egypt | G | 2 | -1 | 3 | ✅ Advance |
| 8 | Uruguay | H | 2 | -2 | 3 | ✅ Advance |
| 9 | United States | D | 1 | -2 | 3 | ❌ Eliminated |
| 10 | Ecuador | E | 1 | -2 | 3 | ❌ Eliminated |
| 11 | DR Congo | K | 1 | -2 | 3 | ❌ Eliminated |
| 12 | Bosnia and Herzegovina | B | 1 | -3 | 3 | ❌ Eliminated |

---

### Knockout Stage

#### Round of 32
| Match | Score | Winner |
|---|---|---|
| South Korea vs Canada | 2-1 | **South Korea** |
| Morocco vs Turkey | 3-2 | **Morocco** |
| Germany vs Netherlands | 2-3 | **Netherlands** |
| Belgium vs Saudi Arabia | 3-1 | **Belgium** |
| Switzerland vs Mexico | 2-1 | **Switzerland** |
| Australia vs Brazil | 2-2 (pen) | **Australia** |
| Japan vs Ivory Coast | 3-1 | **Japan** |
| Spain vs Iran | 3-1 | **Spain** |
| France vs Norway | 3-2 | **France** |
| Argentina vs Haiti | 4-1 | **Argentina** |
| Portugal vs Panama | 3-1 | **Portugal** |
| England vs Tunisia | 2-1 | **England** |
| Senegal vs Austria | 3-2 | **Senegal** |
| Algeria vs South Africa | 3-1 | **Algeria** |
| Colombia vs Egypt | 2-1 | **Colombia** |
| Croatia vs Uruguay | 2-1 | **Croatia** |

#### Round of 16
| Match | Score | Winner |
|---|---|---|
| South Korea vs Morocco | 1-2 | **Morocco** |
| Netherlands vs Belgium | 3-2 | **Netherlands** |
| Switzerland vs Australia | 1-2 | **Australia** |
| Japan vs Spain | 2-3 | **Spain** |
| France vs Argentina | 2-3 | **Argentina** |
| Portugal vs England | 2-2 (pen) | **England** |
| Senegal vs Algeria | 2-2 (pen) | **Algeria** |
| Colombia vs Croatia | 2-2 (pen) | **Croatia** |

#### Quarter-Finals
| Match | Score | Winner |
|---|---|---|
| Morocco vs Netherlands | 2-2 (pen) | **Morocco** |
| Australia vs Spain | 1-3 | **Spain** |
| Argentina vs England | 2-2 (pen) | **Argentina** |
| Algeria vs Croatia | 2-2 (pen) | **Algeria** |

#### Semi-Finals
| Match | Score | Winner |
|---|---|---|
| Morocco vs Spain | 2-3 | **Spain** |
| Argentina vs Algeria | 3-2 | **Argentina** |

#### Third Place Playoff
| Match | Score | Winner |
|---|---|---|
| Morocco vs Algeria | 2-2 (pen) | **Algeria** 🥉 |

#### 🏆 THE FINAL — MetLife Stadium, New Jersey
| Match | Score | Winner |
|---|---|---|
| **Spain vs Argentina** | **2-2 (pen)** | **🏆 Spain** |

### 🏅 Final Podium

| Place | Team |
|---|---|
| 🥇 Champion | **Spain** |
| 🥈 Runner-Up | **Argentina** |
| 🥉 Third Place | **Algeria** |

---

## 📈 Key Findings

- **🥇 Spain** wins the first-ever 48-team World Cup on penalties after a 2-2 draw with Argentina in the final
- **🌍 African Surge**: Morocco reaches the **Semi-Finals** and Algeria claims **3rd Place** — a historic tournament for African football
- **🇦🇺 Australia's Shock Run**: Defeats Brazil on penalties in the R32 and reaches the Quarter-Finals
- **🇫🇷 France Eliminated by Argentina** in a classic R16 rematch (2-3)
- **⚽ High Octane**: The simulation averaged **2.8 goals per match** across the expanded format
- **🎯 Penalty Drama**: 7 knockout matches decided on penalties, reflecting the parity of the expanded tournament

---

## 📦 Data Sources

| File | Records | Source |
|---|---|---|
| `results.csv` | 49,287 matches | [martj42/international-football-results](https://github.com/martj42/international-football-results) |
| `shootouts.csv` | 675 shootouts | Same repository |
| `former_names.csv` | 36 mappings | Custom compiled |

---

*Built with Python 3.11 · Pandas · Scikit-learn · XGBoost · SciPy · Matplotlib*
