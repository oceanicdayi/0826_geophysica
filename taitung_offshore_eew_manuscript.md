# Operational Performance and Magnitude-Bias Mechanism of the Taiwan Earthquake Early Warning System for Offshore Earthquakes: The 25 August 2026 Taitung $M_L$ 5.85 Event

Da-Yi Chen^{1,2}[ORCID: TODO], [TODO: co-author names and ORCIDs]

^1^ Seismological Center, Central Weather Administration, No. 64, Gongyuan Rd., Zhongzheng District, Taipei 100006, Taiwan

^2^ Department of Earth and Life Sciences, University of Taipei, Taipei, Taiwan

**Corresponding author:** Da-Yi Chen, Central Weather Administration, Taipei, Taiwan. E-mail: [TODO]

**Keywords:** Earthquake early warning · Offshore earthquake · Pd magnitude · Radiation pattern · Azimuthal gap · Taiwan

---

## Abstract

Offshore earthquakes are the hardest operational class for earthquake early warning (EEW) because the source lies outside the recording network, yet report-by-report evidence of how operational systems behave under such geometry is scarce. We analyse the complete operational record of the 25 August 2026 Taitung offshore earthquake ($M_L$ 5.85, depth 13.1 km, 48 km off southeastern Taiwan): 83 sequential eBEAR solutions from six parallel processing streams, three dissemination channels, 166 analyst-reviewed intensity observations and per-second intensity for 626 stations. The Central Weather Administration issued its first public alert 13.67 s after origin time simultaneously on all three channels; 92.5% of stations were warned before shaking reached intensity 3, and the cell-broadcast alert covered 17 counties against an observed intensity-3 footprint of 15. The first alert nevertheless reported $M$ 6.6, 0.75 units above the analyst magnitude, and all 166 compared stations were over-warned. Recovering the operational magnitude relation from 2065 single-station records shows that reported magnitude is a strict function of the assumed hypocentral distance: two solutions computed in the same second from identical $Pd$ amplitudes differed by 0.89 magnitude units because their assumed distances differed, and over all solutions epicentral error and reported magnitude correlate at $r=-0.74$. Using the focal mechanism we show that the three stations which set the first magnitude lay on the P-wave radiation maximum, with $|F_P|$ 1.78 times the all-azimuth average, predicting a +0.29 bias against an observed +0.28. Observed peak ground acceleration follows the theoretical S-wave radiation pattern (fitted exponent 1.13, theoretical 1.0; $p<0.001$) with no residual directivity signal ($p=0.92$). A further +0.42 bias persists at the best achievable geometry and recurs in a second offshore event, indicating that offshore paths require separate magnitude calibration. We further show that magnitude error alone and azimuthal gap alone are invalid quality indicators for offshore sources, and propose quality gates based on magnitude-station azimuthal coverage and cross-stream location consistency.

---

## 1. Introduction

Earthquake early warning (EEW) exploits the interval between the fast, weak P wave and the slower, damaging S wave, so its performance is governed by how quickly and how accurately the source can be characterised from the first seconds of P-wave data (Allen and Melgar 2019). For sources inside a dense network the problem is comparatively benign: near-source stations surround the epicentre, azimuthal coverage is good, and the hypocentre is constrained within seconds. For offshore sources, the dominant hazard class along subduction margins, none of these conditions hold: the nearest station may be tens of kilometres away, all stations occupy a limited azimuthal range on land, and both location and magnitude must be inferred from a one-sided sampling of the wavefield. Operational systems worldwide face this geometry, among them SASMEX in Mexico (Espinosa-Aranda et al. 2009), ShakeAlert on the U.S. West Coast (Given et al. 2018) and the Japan Meteorological Agency system, which adopted the wavefield-based PLUM method precisely to stay robust where source parameters are poorly constrained (Kodera et al. 2016).

Taiwan is an instructive laboratory for this problem. The island sits at the convergent boundary between the Eurasian and Philippine Sea plates (Angelier 1986; Kao and Chen 2000); a large share of its felt earthquakes originate offshore in the Ryukyu and Manila subduction systems, whereas the seismic network is necessarily concentrated on land. The Central Weather Administration (CWA) has operated an EEW system for two decades and has published performance milestones mostly for inland shallow events (Wu and Teng 2002; Hsiao et al. 2009, 2011; Chen et al. 2015, 2019). Figure 1 makes the resulting geometry explicit for the event analysed here. The 25 August 2026 Taitung earthquake ($M_L$ 5.85) occurred 48 km east-southeast of Taitung City, outside the land network, with its nearest station 14 km away on Green Island and every remaining station in a single sector to the west and northwest. An inland earthquake of the same size would be enveloped by stations, the nearest one about 5 km away.

![Figure 1](../figures/manuscript/fig01.png)

**Figure 1.** CWA real-time seismic network and the 25 August 2026 Taitung offshore earthquake. Grey circles: strong-motion stations; blue triangles: velocity/broadband stations, as configured in the eBEAR instance analysed here (551 and 228 stations respectively within the map area). Red star: the epicentre of the analysed event; the beachball, plotted offset and connected by a line to the epicentre, shows the focal mechanism used in Section 5.3 (strike 182°, dip 50°, rake 60°). Epicentres of the three comparison events of Section 6 are listed in Table 5.

Most operational EEW magnitudes derive from the amplitude or period of the first few seconds of the P wave. The peak initial displacement $Pd$, measured over a fixed window of typically 3 s, scales with magnitude and distance and is widely used for real-time magnitude estimation (Wu and Kanamori 2005; Wu and Zhao 2006; Zollo et al. 2006). Three limitations are known: saturation when the window is shorter than the rupture duration (Trugman et al. 2019); strong sensitivity to the assumed hypocentral distance, because the distance-correction term is steep; and station-to-station scatter caused by site response and by the source radiation pattern. The last two interact destructively offshore. The earliest triggering stations occupy a narrow azimuth range, so the magnitude is averaged over a single sector of the focal sphere, while any epicentral error translates directly into a distance error and hence into a magnitude error. To our knowledge these two effects have not previously been separated and quantified in an operational record.

This paper closes that gap using the complete operational record of a moderate offshore earthquake. We document the CWA response report by report, covering all six parallel processing streams and all three public dissemination channels; we decompose the first-alert magnitude bias into a location-distance term, an azimuthal-sampling term and an intrinsic relation term; and we test which physical mechanism controls the azimuthal term, using the focal mechanism of the event. We then ask whether the result generalises, by recomputing identical metrics for three further Taiwan earthquakes spanning offshore and near-coast geometries. The outcome is a set of transferable quality-control conclusions: two indicators in routine use, magnitude error and azimuthal gap, are shown to be invalid on their own for offshore sources, and alternatives based on magnitude-station azimuthal coverage and cross-stream location consistency are proposed. Section 2 describes the system and data, Section 3 the methods, Sections 4 to 6 the results, and Sections 7 and 8 the discussion and conclusions.

---

## 2. System and Data

### 2.1 The CWA Real-Time Seismic Network

The CWA real-time network is a mixed-sensor system combining velocity and acceleration instruments in surface, borehole and ocean-bottom installations. Velocity sensors provide sensitivity to weak early P-wave motion, which is decisive for offshore sources; accelerometers preserve waveform fidelity under strong shaking without clipping. Data are digitised at 24 bit, packetised at 1 s, and delivered with typical end-to-end latency of 0.5–2 s. Real-time processing runs within the Earthworm framework (Johnson et al. 1995). By 2025 the network comprised 603 accelerometers, 179 velocity stations and 9 ocean-bottom stations. The instance analysed here was configured with 551 strong-motion and 228 velocity/broadband stations inside the map area of Figure 1; their distribution is dense on the island but, as that figure shows, provides no coverage seaward of the east coast.

### 2.2 eBEAR Architecture and Parallel Streams

The earthworm-Based Earthquake Alarm Reporting (eBEAR) system (Chen et al. 2015) runs as multiple parallel instances that share the same real-time data feed but differ in association parameters and location algorithm. Two location families operate simultaneously:

- the **effective-epicentre (geometric-centre) method** (`f42`, `f43`), which returns the centroid of triggered stations with depth fixed at 10 km, is immediate and robust against non-convergence (Chen et al. 2019);
- the **Geiger inversion method** (`gei`), which solves for the hypocentre iteratively and can resolve depth but requires a usable station geometry.

For the event analysed here, six streams ran in parallel on four computers: `192_f43`, `192_gei`, `230_f42`, `230_gei`, `231_gei` and `236_gei`. Each stream writes one report file (`.rep`) per solution, containing the source parameters, the number of triggered stations $n$, the number of stations used for magnitude $n_m$, the azimuthal gap, and a per-station table of $Pa$, $Pv$, $Pd$, single-station magnitude $M_{Pd}$ and assumed hypocentral distance $R$. This makes the operational magnitude fully auditable at station level, which is the basis of the analysis in Section 5.

Three magnitudes are computed: $M_{Pd}$ from peak initial displacement, $M_{tc}$ from the characteristic period $\tau_c$, and a combined $M_{all}$. **The disseminated magnitude is $M_{Pd}$.**

### 2.3 Dissemination Channels

Alerts are distributed through three independent channels with different thresholds: (i) the Public Warning System (PWS) cell-broadcast, nominally for $M\geq5.0$ and predicted intensity $\geq3$ (Taipei $\geq2$); (ii) a television channel (CAP), nominally $M\geq5.0$ and predicted intensity $\geq2$; and (iii) a school channel (XML via a dedicated network), nominally $M\geq4.5$ and predicted intensity $\geq2$. The school channel transmits successive updates, whereas PWS and TV normally issue a single message per event.

### 2.4 Data Used

| Data set | Content | Use |
| --- | --- | --- |
| eBEAR report files | 83 solutions from 6 streams, including 2065 single-station records | Source convergence, magnitude decomposition |
| Analyst-reviewed P-file (`.sdp`) | 290 phases, 166 stations with observed intensity and PGA, azimuth and take-off angle per station | Reference solution, radiation-pattern test |
| Issue-sequence log | The subset of solutions promoted to dissemination | Alert timing |
| CAP / XML alert files | 1 PWS, 1 TV, 4 school messages | Dissemination performance, coverage |
| Per-second intensity JSON | 626 stations, 120 s, 1 s sampling | Response timeliness, blind-zone analysis |
| Focal mechanism | strike 182°, dip 50°, rake 60° | Radiation-pattern test |

Three additional archived events (Section 6) provide the comparison baseline. For every event, reference hypocentre and magnitude are read directly from that event's analyst-reviewed P-file header so that all events are treated identically.

---

## 3. Methods

### 3.1 Reference Solution and Metric Definitions

The reference (ground truth) is the CWA analyst-reviewed solution. For the Taitung event this is 2026-08-25 07:00:11.33 UTC, 22.6252°N, 121.5968°E, depth 13.05 km, $M_L$ 5.85, based on 290 phases with azimuthal gap 105°, rms 0.11 s and quality grade B; it agrees with the published CWA catalogue entry (report No. 115057; $M$ 5.8, 48.0 km east-southeast of Taitung).

We define:

- **latency** of a solution = its reporting time minus the reference origin time;
- **alert latency** = the `sent` timestamp written in the CAP or XML alert product minus the reference origin time. This is the instant at which the product left the warning system; it excludes downstream carrier delivery time for cell broadcast, which is not recorded in the products analysed here. All events in this study are measured identically, so cross-event comparisons are internally consistent;
- **epicentral error** = horizontal distance between the solution and the reference epicentre;
- **magnitude bias** $\Delta M = M_{Pd} - M_L^{\mathrm{ref}}$;
- **well-located solution** = epicentral error < 10 km;
- **converged value** = median of the last three well-located solutions of the event;
- **geometry penalty** = magnitude of the earliest well-located solution minus the converged magnitude.

### 3.2 Recovering the Operational Magnitude Relation

Because each report lists $Pd$, $R$ and $M_{Pd}$ per station, the operational relation can be recovered by least squares over all 2065 single-station records of the event:

$$M_{Pd} = 4.79 + 1.16\,\log_{10}(Pd) + 1.85\,\log_{10}(R), \qquad \mathrm{rms}=0.13$$

with $Pd$ in cm and $R$ in km. Predicted and reported values lie on the 1:1 line (Fig. 8d), confirming that the operational magnitude is a deterministic function of $Pd$ and assumed distance. The coefficient 1.85 on $\log_{10}R$ implies that a factor-of-two error in assumed distance produces 0.56 magnitude units of error. This relation is used only as a diagnostic description of the operational system, not as a proposed new scaling law.

### 3.3 Radiation-Pattern Computation

Far-field P- and S-wave radiation coefficients $F_P$, $F_{SV}$, $F_{SH}$ are computed from the focal mechanism following Aki and Richards (2002, Box 4.4), with the take-off angle measured from the downward vertical. Take-off angles for the 166 analyst-reviewed stations are taken from the P-file (velocity-model values); for report-file stations they are interpolated from the P-file distance–take-off relation. Because observed amplitudes never vanish on nodal planes, $|F|$ is floored at 0.10 in regressions. We use $|F_S|=\sqrt{F_{SV}^2+F_{SH}^2}$ against observed PGA (S-wave dominated) and $|F_P|$ against $Pd$ (P-wave).

### 3.4 Statistical Tests

Coefficient uncertainties are estimated by bootstrap resampling (4000 iterations). Significance of an azimuthal or radiation term is assessed by permutation (4000 iterations), shuffling the association between stations and the tested predictor and comparing the resulting rms improvement (or azimuthal harmonic amplitude) with the observed value. Azimuthal structure is quantified by the amplitude of the best-fitting one-cycle harmonic, $y=a+b\cos\phi+c\sin\phi$, amplitude $\sqrt{b^2+c^2}$.

### 3.5 Cross-Event Protocol

Four events with complete report archives are compared (Section 6). For each, all metrics are recomputed from the raw report files and that event's own analyst P-file using identical code, so the comparison is not affected by differences in how individual events were catalogued.

---

## 4. The 25 August 2026 Taitung Offshore Earthquake

### 4.1 Event and Observed Shaking

The earthquake occurred at 15:00:11.33 local time (07:00:11.33 UTC) 48 km east-southeast of Taitung City at 13.1 km depth, with $M_L$ 5.85. It is a reverse-faulting event with a small strike-slip component (strike 182°, dip 50°, rake 60°); the P axis is nearly horizontal at azimuth 293°, consistent with the regional convergence direction. The nearest station, on Green Island (LDU, 14.1 km), recorded 150.1 gal and intensity 4 — the largest ground motion of the event. Of the 166 analyst-reviewed stations, 6 reached intensity 4, 13 reached intensity 3, and the remainder were at intensity 2 or below.

![Figure 2](../figures/manuscript/fig02.png)

**Figure 2.** PWS coverage of the first alert (17 counties, shaded) with the epicentre (star) and dashed circles showing the S-wave response-time contours at 10 s intervals from the alert instant. The 0 s contour marks the theoretical blind zone boundary.

### 4.2 Alert Timeline and Coverage

All three channels issued their first message at 07:00:25 UTC, i.e. **13.67 s after the origin time**. The first internal solution was available at 12.52 s. The school channel then issued three updates at 14.67 s, 14.67 s and 17.67 s.

| Channel | Messages | First alert (s) | Coverage |
| --- | ---: | ---: | --- |
| PWS (cell broadcast) | 1 | 13.67 | 17 counties/cities |
| Television (CAP) | 1 | 13.67 | 11 counties/cities |
| School (XML) | 4 | 13.67 | 12 counties at predicted intensity ≥ 3 |

**Table 1.** Dissemination summary. The three channels dispatched simultaneously; the entire alert delay is therefore upstream of the publication pipeline.

Fifteen counties eventually recorded intensity 3 or above. PWS coverage (17) therefore exceeded the observed footprint (15): the alert was conservative rather than under-inclusive.

![Figure 3](../figures/manuscript/fig03.png)

**Figure 3.** Cumulative number of alerted counties for the three channels compared with the observed cumulative count of counties first exceeding intensity 3 (per-second intensity data). All channels reach their final coverage at 13.7 s, whereas the observed footprint grows until about 65 s. The first county exceeded intensity 3 at about 4 s, before any alert was issued.

### 4.3 Source-Parameter Convergence

Eighty-three solutions were produced by six streams within 40 s. Location convergence was rapid for the Geiger streams and poor for the geometric-centre streams: `192_gei` was within 4.6 km of the reference in its first solution at 12.5 s, whereas `192_f43` placed the epicentre 35.4 km inland and never recovered (final error 36.1 km). Final errors for the four converging streams were 0.8–1.9 km.

![Figure 4](../figures/manuscript/fig04.png)

**Figure 4.** Epicentre convergence trajectories of the six parallel streams. The reference epicentre is the yellow star. Early geometric-centre solutions lie on land, 35–43 km northwest of the true offshore source.

![Figure 5](../figures/manuscript/fig05.png)

**Figure 5.** Evolution of (a) magnitude, (b) horizontal location error, (c) depth and (d) station count versus latency for the six streams. Magnitude stabilises at 6.1–6.4 against the reference 5.85; depth remains at the 10/20/30 km grid nodes.

### 4.4 Intensity Prediction

Predicted intensities from each school message were compared with the 166 analyst-reviewed observations.

| Report | Magnitude / depth | Exact (%) | Within ±1 (%) |
| --- | --- | ---: | ---: |
| 1 (13.67 s) | $M$ 6.6 / 30 km | 10.2 | **59.0** |
| 2 (14.67 s) | $M$ 5.9 / 20 km | 27.1 | 75.9 |
| 3 (14.67 s) | $M$ 6.1 / 20 km | 24.7 | 75.9 |
| 4 (17.67 s) | $M$ 5.9 / 20 km | 37.4 | 80.7 |

**Table 2.** Intensity prediction accuracy per school-channel report (166 compared stations).

The residual distribution of the first report is entirely non-negative: **no station was under-warned, and most were over-warned by one to two intensity ranks** (Fig. 6). Accuracy improved monotonically with each update, but the message that reached the public was the least accurate one.

![Figure 6](../figures/manuscript/fig06.png)

**Figure 6.** Intensity residual (predicted minus observed) distributions for the first and second reports. The first report is entirely non-negative.

### 4.5 Response Timeliness and the Blind Zone

Using the per-second observed intensity of 626 stations, the first issued solution preceded the S-wave arrival at 99.0% of stations (median lead 33.6 s) and preceded the crossing of intensity 3 at **92.5%** of the stations that eventually reached intensity 3 (median lead 29.1 s).

The exception is the near-source zone. Taitung City, 48.7 km from the epicentre, had a theoretical lead time of only 2.1 s relative to the 13.67 s alert; Green Island and the Taitung coast exceeded intensity 4–5 within 4–13 s, i.e. before the alert was issued (Fig. 7). Because the population within the blind zone is small, the practical impact was limited, but the geometry is intrinsic: for an offshore source the closest exposed community is also the least protected.

![Figure 7](../figures/manuscript/fig07.png)

**Figure 7.** Per-second maximum observed intensity by latitude band, with the alert times superimposed. Intensity 5 is reached in the 22.6°N band within about 4 s, well before the first alert at 13.7 s.

### 4.6 A Favourable Design Choice

The disseminated solution reported $M_{Pd}$ 6.58, but the same report also contained $M_{tc}$ 7.63 and the combined $M_{all}$ 7.10. Because CWA disseminates $M_{Pd}$, the public alert was $M$ 6.6 rather than $M$ 7.1. $M_{tc}$ reached 8.5 in three early solutions of this event. This confirms the operational value of restricting dissemination to the more stable amplitude-based magnitude during the first seconds.

---

## 5. Magnitude Bias: Decomposition and Mechanism

### 5.1 Reported Magnitude Is a Function of the Assumed Distance

The clearest evidence is an internal control experiment provided by the operational system itself. At 07:00:23.8 UTC, computer 192 produced two solutions in the same second, `192_gei` and `192_f43`, from the **same stations with identical $Pd$ values**. Their only difference was the assumed hypocentre.

| Station | $Pd$ (cm) | `gei` $R$ (km) | `gei` $M_{Pd}$ | `f43` $R$ (km) | `f43` $M_{Pd}$ |
| --- | ---: | ---: | ---: | ---: | ---: |
| G035 | 0.06748 | 55 | 6.63 | 15 | 5.66 |
| G036 | 0.06561 | 54 | 6.59 | 16 | 5.67 |
| G047 | 0.04337 | 60 | 6.45 | 21 | 5.64 |
| G046 | 0.02910 | 60 | 6.23 | 21 | 5.43 |
| **Event magnitude** | | | **6.55** | | **5.66** |

**Table 3.** Identical amplitudes, different assumed distances. The 0.89-unit difference equals $1.85\log_{10}(60/21)=0.84$ predicted by the operational relation.

Critically, the solution that appeared *accurate* (`f43`, $M$ 5.66 against $M_L$ 5.85) was the badly mislocated one (35.4 km error), while the solution that was *correctly located* (`gei`, 4.6 km error) over-estimated. The same behaviour appears within a single stream: when `192_f43` briefly converged to within 1.1 km at its fourth solution, its magnitude jumped from 5.46 to 6.42, and fell back to 5.81 when the location drifted offshore-to-inland again.

Over all 83 solutions, epicentral error and reported magnitude correlate at $r=-0.74$, with a slope of −0.15 magnitude units per 10 km of location error (Fig. 8c). The regression crosses the reference magnitude at an epicentral error of about 30 km: **for this event, the apparently most accurate magnitudes were produced by solutions mislocated by 30 km.**

![Figure 8](../figures/manuscript/fig08.png)

**Figure 8.** Evidence that reported magnitude tracks assumed distance. (a) Two solutions computed in the same second from identical $Pd$ values. (b) Magnitude and location error report by report for stream `192_f43`. (c) All 83 solutions, $r=-0.74$. (d) Recovered operational relation, 2065 single-station records, rms 0.13.

### 5.2 One-Sided Sampling and the Azimuthal-Gap Penalty

The first disseminated solution used only three stations for magnitude ($n_m=3$) at azimuths 295–307° from the epicentre, i.e. within a 12° sector. The nearest station, LDU (14.1 km, azimuth 292°), was effectively unusable: it recorded $Pa$ = 162.3 gal and $Pv$ = 4.73 cm s⁻¹ but $Pd$ = 0.0006 cm, yielding a single-station magnitude of 3.46 — an integration or saturation failure at the one station that could have anchored the estimate downward.

Grouping the 72 single-station magnitudes of the final, well-located solution by azimuth sector and distance band shows that magnitude estimates vary by 0.3–0.5 units between sectors at the same distance, and that the sector used by the first report (west-northwest, < 60 km) is the highest of all (median 6.54). Stations beyond 150 km yield 5.4–5.9, but they only join the solution after the eleventh report.

Separating the 83 solutions by location accuracy shows that azimuthal gap itself is a weak predictor when the location is correct (slope +0.07 magnitude units per 100° of gap, $r=0.23$) and only matters at the extreme (> 300°, where $n_m\leq4$; mean bias +0.57). Among poorly located solutions the apparent correlation is strong ($r=0.76$) but spurious: **the six solutions with the smallest gaps (125–139°) are the six with the largest location errors (mean 41 km)**, because placing the epicentre inside the land network artificially improves its apparent azimuthal coverage.

![Figure 9](../figures/manuscript/fig09.png)

**Figure 9.** Azimuthal evidence. (a) Station azimuth coverage: no station exists between 45° and 180°; red lines mark the three stations that set the first magnitude. (b) Median single-station magnitude by azimuth sector and distance band. (c) Azimuth versus single-station magnitude residual for the final solution. (d) Direction of the strongest distance-corrected observed PGA per distance band.

### 5.3 The Azimuthal Effect Is Controlled by the Radiation Pattern, Not by Directivity

The focal mechanism resolves the mechanism question. The P axis (azimuth 293°, plunge 1°) points directly at the sector occupied by the first-report stations, and P-wave radiation maximises along the P and T axes. The theoretical radiation coefficients are:

| Station | Azimuth | Take-off | $|F_P|$ |
| --- | ---: | ---: | ---: |
| G036 | 295° | 68° | 0.748 |
| G047 | 297° | 70° | 0.790 |
| G035 | 307° | 65° | 0.559 |
| **Mean of the three** | | | **0.699** |
| Network median (72 stations) | | | 0.447 |
| All-azimuth average | | | 0.392 |

**Table 4.** The three stations that set the first magnitude sat on the maximum lobe of the P-wave radiation pattern. The ratio 0.699/0.392 = 1.78 predicts a magnitude bias of $1.16\log_{10}(1.78)=+0.29$.

Three independent tests support the radiation-pattern interpretation:

1. **Observed ground motion follows the radiation pattern.** Regressing $\log_{10}(\mathrm{PGA})$ of the 117 stations with non-zero PGA on $\log_{10}R$ and $\log_{10}|F_S|$ (using the P-file take-off angles) reduces the rms from 0.308 to 0.277 (10.2%), with a fitted exponent of $+1.13$ (bootstrap 95% CI 0.60–1.68), statistically indistinguishable from the theoretical value 1.0; permutation $p<0.001$. A mechanism-free azimuthal harmonic explains less (7.7%).
2. **No directivity signal remains.** After removing distance and the radiation pattern, the residual azimuthal harmonic amplitude drops from 0.453 to 0.028 $\log_{10}$ units ($p=0.92$). Within the sampled azimuth range there is no detectable rupture-directivity contribution — as expected for an $M_L$ 5.85 rupture of about 4–5 km length and 2 s duration measured in a 3 s window.
3. **The predicted bias matches the observed one.** The radiation-pattern prediction (+0.29) equals, within 0.01, the geometry penalty measured from the convergence of stream `192_gei` (+0.28; Section 5.4).

![Figure 10](../figures/manuscript/fig10.png)

**Figure 10.** Radiation pattern and the magnitude stations. (a) Lower-hemisphere P-wave radiation pattern with the 166 analyst-reviewed stations (grey) and the three first-report stations (red stars, with $|F_P|$); the stars lie adjacent to the P axis. (b) $|F_P|$ and $|F_S|$ versus azimuth; outer ticks are station azimuths, showing the empty 45–180° sector. (c) Distance-corrected observed PGA versus theoretical $|F_S|$, slope $+1.11$ (multivariate $+1.13$). (d) Azimuthal residuals before and after removing the radiation pattern.

For completeness, regressing report-file $Pd$ directly on $|F_P|$ is not significant ($p=0.123$; 1.8% rms improvement), which we attribute to the large scatter of 3 s $Pd$ (rms 0.57 in $\log_{10}$), interpolated take-off angles, and the non-zero amplitudes near nodal planes. The direct statistical evidence for the radiation-pattern control therefore rests on the S-wave/PGA data set, supported by the quantitative agreement in item 3.

### 5.4 Error Budget of the First Alert

Stream `192_gei` provides a clean measurement of what improving the geometry can and cannot buy. Its first solution (3 magnitude stations, 335° gap, 4.6 km location error) reported 6.55; its nineteenth solution (32 magnitude stations, 100° gap, 0.9 km location error) reported 6.27, and its last seven solutions averaged 6.30 with a standard deviation of 0.035. The system converged completely — but to a biased value.

$$\underbrace{5.85}_{\text{analyst } M_L} + \underbrace{0.42}_{\text{$Pd$ relation bias}} + \underbrace{0.28}_{\text{one-sided sampling}} = \underbrace{6.55}_{\text{first solution}}$$

![Figure 11](../figures/manuscript/fig11.png)

**Figure 11.** Error budget of the first alert. The +0.42 term is independent of station geometry; the +0.28 term is the azimuthal-sampling penalty, quantitatively explained by the radiation pattern (+0.29 predicted).

The +0.42 residual persists at the best geometry the event ever achieved and is therefore a property of the $Pd$ relation for this offshore path, not of the station distribution. Improving the network or waiting for more reports cannot remove it; only calibration can.

---

## 6. Cross-Event Comparison

To test whether the offshore bias is event-specific, we recomputed all metrics for three further Taiwan events with complete report archives, using each event's own analyst P-file as reference.

| | **Taitung 2026** | **Yilan 2025** | Hualien 2026a | Hualien 2026b |
| --- | ---: | ---: | ---: | ---: |
| Source class | offshore | offshore, deep | near-coast | inland |
| Epicentre (°N, °E) | 22.6252, 121.5968 | 24.6622, 122.0043 | 24.0437, 121.6313 | 24.0235, 121.6170 |
| $M_L$ (analyst) | 5.85 | 7.01 | 5.74 | 5.01 |
| Depth (km) | 13.1 | 67.7 | 25.4 | 15.8 |
| Nearest station (km) | 14.1 | 15.8 | 5.0 | 5.2 |
| Analyst azimuthal gap (°) | 105 | 70 | 86 | 100 |
| Solutions analysed | 83 | 104 | 81 | 67 |
| First internal solution (s) | 12.52 | 14.07 | 7.97 | 7.90 |
| First public alert (s) | 13.67 | 13.77 | 8.27 | 8.26 |
| Well-located solutions | 54 | 31 | 80 | 60 |
| **Mean $\Delta M$, well located** | **+0.38 ± 0.17** | **+0.45 ± 0.14** | **−0.08 ± 0.17** | **−0.07 ± 0.16** |
| $r$ (epicentral error, $M_{Pd}$) | **−0.74** | **−0.55** | +0.23 | +0.46 |
| First-report intensity within ±1 (%) | 59.0 | 88.1 | 92.6 | 92.4 |
| Stations warned before intensity 3 (%) | 92.5 | 82.6 | 92.5 | 64.2 |

**Table 5.** Cross-event comparison. All reference parameters are read from each event's analyst-reviewed P-file; all metrics are recomputed with identical code. "First public alert" is the earliest `sent` timestamp among the three channels; for the Taitung and Yilan events all channels dispatched simultaneously, whereas for Hualien 2026b the school channel led (8.26 s) and the PWS message followed at 17.26 s.

Three patterns emerge (Fig. 12):

1. **The magnitude bias is a property of offshore geometry, not of the system.** Both offshore events over-estimate among well-located solutions (+0.38, +0.45); both near-coast events, whose nearest station is 5 km away, are unbiased (−0.08, −0.07). The discriminating variable is the distance to the nearest station, i.e. whether the source is inside or outside the network.
2. **The mislocation–magnitude compensation is specific to offshore sources.** Only the offshore events show negative correlation between epicentral error and reported magnitude, because their mislocations are systematically directed *toward* the network. Inland events, whose mislocations are unsystematic, show weak positive correlations.
3. **Offshore geometry costs 4–6 s of alert latency**, consistently: 12.5–14.1 s for the two offshore events versus 7.9–8.0 s for the two near-coast events.

![Figure 12](../figures/manuscript/fig12.png)

**Figure 12.** Cross-event comparison. (a) Magnitude bias of well-located solutions versus the distance to the nearest station. (b) First internal solution and first public alert latency. (c) Correlation between epicentral error and reported magnitude. (d) Magnitude bias versus latency for well-located solutions only.

We emphasise that four events cannot establish a population statistic; the comparison is a case-controlled contrast (two offshore, two near-coast) designed to test whether the mechanism identified for the Taitung event generalises within Taiwan's own operational record.

---

## 7. Discussion

### 7.1 Why Offshore Geometry Biases $Pd$ Magnitude

The three terms measured here act in the same direction for an offshore source and in different directions for an inland source:

- **Distance term.** Offshore mislocation is systematically toward the land network, so it lowers the assumed distance and therefore the magnitude. Any location improvement raises the magnitude. Inland mislocations have no preferred direction, so this term averages out (Table 5, row $r$).
- **Azimuthal-sampling term.** For an offshore source, the earliest triggering stations necessarily occupy one sector of the focal sphere. Whether the resulting magnitude is biased high or low is then set by where that sector falls on the radiation pattern. Here it fell on the P-axis lobe (+0.29). Had the same geometry sampled a nodal direction — azimuth 210° has $|F_P|=0.01$ in this mechanism — the first magnitude would have been strongly **under**-estimated, with a corresponding risk of missed warning.
- **Relation term.** The persistent +0.42 for the Taitung event and +0.45 for the Yilan event indicates that the operational $Pd$ scaling, calibrated principally on inland paths, over-predicts magnitude for offshore paths. Whether this reflects path attenuation, near-source station siting or the depth/distance range of the calibration data set cannot be resolved from four events.

An important corollary is that the sign of the initial bias is not universal: the two near-coast events start below the reference and rise toward it, whereas the Taitung event starts above and falls toward a biased plateau (Fig. 12d). Bias direction is a geometric accident of which stations trigger first.

### 7.2 Magnitude Error Is Not a Valid Quality Metric

This is the most immediately transferable finding. In the Taitung event, the absolute magnitude error of the *poorly located* solutions (mean 0.21) was **smaller** than that of the *well located* solutions (0.38), purely because distance under-estimation cancelled the relation bias. A verification procedure that ranks solutions by magnitude error alone would therefore select the worst solutions. Operational verification must evaluate location error and magnitude error jointly; we recommend reporting them as a pair for every solution.

### 7.3 Azimuthal Gap Is Not a Reliable Quality Indicator Offshore

Azimuthal gap is widely used as a solution-quality flag. For sources outside the network it can be actively misleading: a correct offshore solution necessarily has a large gap (the minimum achieved in this event was 100°), whereas an incorrect solution placed inside the network acquires a small gap. In our data the six smallest-gap solutions were the six worst-located ones. Gap should be interpreted jointly with whether the epicentre lies inside or outside the station polygon, and should not be used alone as a promotion criterion.

### 7.4 Transferable Operational Recommendations

| Priority | Recommendation | Evidence |
| --- | --- | --- |
| High | Apply an offshore-specific magnitude correction (here −0.3 to −0.4), validated on additional events before deployment | +0.38 and +0.45 residual bias in two offshore events at the best achievable geometry |
| High | Require a minimum magnitude-station count and azimuthal spread (e.g. $n_m\geq5$ spanning ≥ 2 quadrants) before promoting a magnitude to public dissemination | $n_m\leq4$ solutions have $\Delta M$ scatter 0.41 versus 0.23 for $n_m\geq5$; first alert used $n_m=3$ within a 12° sector |
| High | Detect and repair $Pd$ integration/saturation failures at near-source high-gain stations in real time | LDU recorded 162 gal but returned $Pd$ = 0.0006 cm, removing the only near-source constraint |
| Medium | Use cross-stream location consistency (e.g. two independent streams within 15 km) as the promotion gate instead of gap | At 07:00:24 the two streams of computer 192 differed by 35 km, a detectable inconsistency |
| Medium | Report location error and magnitude error jointly in verification | Section 7.2 |
| Medium | Prefer the amplitude-based magnitude over $\tau_c$-based or combined magnitudes in the first seconds | $M_{tc}$ reached 8.5; $M_{all}$ would have produced $M$ 7.1 instead of $M$ 6.6 |
| Medium | Use median or trimmed-mean station magnitude rather than the mean of a few stations | With three stations, a single 0.5-unit outlier shifts the event magnitude by 0.17 |

Where a focal mechanism becomes available within seconds — as is increasingly feasible for moderate events near dense networks — weighting station magnitudes by the theoretical radiation coefficient would remove the sampling term directly. In its absence, azimuthal spread requirements achieve much of the same effect, because the four-lobed radiation pattern averages out over quadrants.

### 7.5 What Worked

Three aspects of the CWA implementation performed well and are worth documenting for other operators:

1. **Parallel heterogeneous streams.** The geometric-centre streams provided immediate solutions; the Geiger streams provided the only accurate offshore location. Running both, and promoting from whichever satisfies quality gates, is a robust design for source regions where one method systematically fails.
2. **Simultaneous multi-channel dispatch.** PWS, television and school alerts left the system in the same second, so no channel-specific delay was incurred; the entire 13.67 s was source-estimation time.
3. **Conservative coverage.** PWS reached 17 counties against an observed intensity-3 footprint of 15. The over-estimate produced over-alerting rather than missed alerting — the preferable failure direction, although repeated over-alerting carries its own long-term cost in public credibility.

### 7.6 Limitations

1. The mechanism analysis rests on a single event with a single focal mechanism; the radiation-pattern control is demonstrated for this geometry, not proven as a general rule.
2. Azimuths between 45° and 180° contain no stations, so a directivity lobe pointing east-southeast could not be detected. Our statement is that no directivity signal is required to explain the observations within the sampled azimuth range.
3. Site response is not modelled separately; the residual rms of 0.277 after the radiation-pattern correction certainly contains site and path terms.
4. Four events are too few for a population statistic. The consistent contrast between two offshore and two near-coast events is suggestive, not conclusive.
5. The recovered $Pd$ relation describes the operational implementation of one system; the coefficients should not be transferred to other systems.

---

## 8. Conclusions

We analysed the complete operational record of the 25 August 2026 Taitung offshore $M_L$ 5.85 earthquake — 83 eBEAR solutions from six parallel streams, three dissemination channels, 166 analyst-reviewed intensity observations and per-second intensity for 626 stations — and reached four conclusions.

1. **Operationally, the system performed as designed for an offshore source.** The first public alert was issued 13.67 s after the origin time simultaneously through all three channels; 92.5% of stations were warned before shaking reached intensity 3, with a median lead of 29 s; coverage (17 counties) exceeded the observed intensity-3 footprint (15 counties). The blind zone was confined to the near-source offshore area and Taitung City (2.1 s lead).
2. **The first alert over-estimated magnitude by 0.75 units, and the bias decomposes cleanly.** A +0.42 term arises from the $Pd$ scaling relation itself and survives at the best achievable geometry; a +0.28 term arises from one-sided azimuthal sampling.
3. **The sampling term is controlled by the source radiation pattern.** The three stations that set the first magnitude lay on the P-wave maximum lobe ($|F_P|$ 1.78 times the all-azimuth average), predicting +0.29 against an observed +0.28. Observed PGA follows the theoretical S-wave radiation pattern with an exponent of 1.13 (theoretical 1.0), and no residual azimuthal signal remains, excluding rupture directivity.
4. **Two widely used quality indicators fail for offshore sources.** Magnitude error alone selects the worst-located solutions, because mislocation toward the network compensates the relation bias ($r=-0.74$); and azimuthal gap alone rewards solutions that have been incorrectly placed inside the network.

For subduction-margin EEW operators, the practical implications are to calibrate magnitude separately for offshore paths, to gate dissemination on the number and azimuthal spread of magnitude stations rather than on gap, to verify location and magnitude jointly, and to monitor near-source high-gain channels for amplitude-integration failures. These measures are inexpensive relative to network expansion and address the dominant error terms identified here.

---

## Declarations

**Funding** [TODO: grant numbers and funding bodies, or state that no funding was received.]

**Competing interests** The authors declare no competing interests.

**Ethics approval** Not applicable.

**Consent to participate / Consent for publication** Not applicable.

**Data availability** The eBEAR operation logs (83 report files for the Taitung event and 252 for the three comparison events), the analyst-reviewed P-files, the alert products (`CWA-EEW115006201`-`204` and the corresponding PWS and TV CAP files) and the per-second intensity files are maintained by the Central Weather Administration and are available from the corresponding author on reasonable request. Derived data tables underlying every figure are provided as supplementary material.

**Code availability** The analysis code that produces every figure and table in this paper is available from the corresponding author on reasonable request.

**Author contributions** [TODO: e.g. D.-Y.C. designed the study, performed the analysis and wrote the manuscript; ... All authors reviewed and approved the final manuscript.]

**Use of generative AI** [TODO: Springer Nature requires disclosure of the use of generative AI in the writing process. Adjust or delete this statement as appropriate: generative AI tools were used to assist with drafting, code development and figure production; the authors verified all data, analyses and interpretations and take full responsibility for the content.]

## Acknowledgements

[TODO: colleagues who contributed to EEW system operation and data curation.]

## References

*Note to co-authors: volume, page and DOI details of the internationally published items below should be verified against the publisher record before submission.*

Aki K, Richards PG (2002) Quantitative seismology, 2nd edn. University Science Books, Sausalito

Allen RM, Melgar D (2019) Earthquake early warning: advances, scientific challenges, and societal needs. Annu Rev Earth Planet Sci 47:361-388

Angelier J (1986) Geodynamics of the Eurasia-Philippine Sea plate boundary: preface. Tectonophysics 125:IX-X

Chen DY, Hsiao NC, Wu YM (2015) The Earthworm based earthquake alarm reporting system in Taiwan. Bull Seismol Soc Am 105(2A):568-579

Chen DY, Lin TL, Wu YM, Hsiao NC (2019) Testing a P-wave earthquake early warning system by simulating the 2018 Hualien earthquake. Seismol Res Lett 90(6):2232-2238

Espinosa-Aranda JM, Cuellar A, Garcia A, Ibarrola G, Islas R, Maldonado S, Rodriguez FH (2009) Evolution of the Mexican seismic alert system (SASMEX). Seismol Res Lett 80(5):718-726

Given DD, Allen RM, Baltay AS, Bodin P, Cochran ES, Creager K, de Groot RM, Gee LS, Hauksson E, Heaton TH, Hellweg M, Murray JR, Thomas VI, Toomey D, Yelin TS (2018) Revised technical implementation plan for the ShakeAlert system - an earthquake early warning system for the West Coast of the United States. US Geol Surv Open-File Rep 2018-1155

Hsiao NC, Wu YM, Shin TC, Zhao L, Teng TL (2009) Development of earthquake early warning system in Taiwan. Geophys Res Lett 36:L00B02

Hsiao NC, Wu YM, Zhao L, Chen DY, Huang WT, Kuo KH, Shin TC, Leu PL (2011) A new prototype system for earthquake early warning in Taiwan. Soil Dyn Earthq Eng 31:201-208

Johnson CE, Bittenbinder A, Bogaert B, Dietz L, Kohler W (1995) Earthworm: a flexible approach to seismic network processing. IRIS Newsl 14(2):1-4

Kao H, Chen WP (2000) The Chi-Chi earthquake sequence: active, out-of-sequence thrust faulting in Taiwan. Science 288(5475):2346-2349

Kodera Y, Yamada Y, Hirano K, Tamaribuchi K, Adachi S, Hayashimoto N, Morimoto M, Nakamura M, Hoshiba M (2016) The propagation of local undamped motion (PLUM) method: a simple and robust seismic wavefield estimation approach for earthquake early warning. Bull Seismol Soc Am 106(3):972-986

Minson SE, Meier MA, Baltay AS, Hanks TC, Cochran ES (2018) The limits of earthquake early warning: timeliness of ground motion estimates. Sci Adv 4(3):eaaq0504

Trugman DT, Page MT, Minson SE, Cochran ES (2019) Peak ground displacement saturates exactly when we want it to. J Geophys Res Solid Earth 124:4642-4653

Wu YM, Kanamori H (2005) Experiment on an onsite early warning method for the Taiwan early warning system. Bull Seismol Soc Am 95(1):347-353

Wu YM, Teng TL (2002) A virtual subnetwork approach to earthquake early warning. Bull Seismol Soc Am 92(5):2008-2018

Wu YM, Zhao L (2006) Magnitude estimation using the first three seconds P-wave amplitude in earthquake early warning. Geophys Res Lett 33:L16312

Zollo A, Lancieri M, Nielsen S (2006) Earthquake magnitude estimation from peak amplitudes of very early seismic signals on strong motion records. Geophys Res Lett 33:L23312

---

## Submission checklist (remove before submission)

Items that must be applied in the Word file rather than in this markdown source:

1. Double line spacing and continuous line numbers throughout the manuscript file.
2. Figures uploaded as separate files, at least 300 dpi for halftone and 600-1200 dpi for line art (EPS, TIFF or high-resolution PNG); captions collected at the end of the text file as required by the journal.
3. Tables as editable text (not images), each with its caption above the table and cited in numerical order.
4. Title page with all author names, ORCID identifiers, full affiliation addresses and the corresponding author's e-mail.
5. Confirm the journal's current abstract word limit (this abstract is about 290 words) and keyword count (six are supplied).
6. Verify the reference style against the current Acta Geophysica guide for authors; the list below follows the Springer basic author-date style with abbreviated journal titles.
7. Add DOIs to all references where available.
8. Supplementary material: the per-report data tables (`cross_event_summary.csv`, `magnitude_relations.csv`, `radiation_pattern_stations.csv`) are candidates for deposition.
