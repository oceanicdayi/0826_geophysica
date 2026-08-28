# Operational Performance and Magnitude-Bias Mechanism of the Taiwan Earthquake Early Warning System for Offshore Earthquakes: The 25 August 2026 Taitung $M_L$ 5.85 Event

Da-Yi Chen^{1,2}[ORCID: TODO], [TODO: co-author names and ORCIDs]

^1^ Seismological Center, Central Weather Administration, No. 64, Gongyuan Rd., Zhongzheng District, Taipei 100006, Taiwan

^2^ Department of Earth and Life Sciences, University of Taipei, Taipei, Taiwan

**Corresponding author:** Da-Yi Chen, Central Weather Administration, Taipei, Taiwan. E-mail: [TODO]

**Keywords:** Earthquake early warning · Offshore earthquake · Pd magnitude · Radiation pattern · Azimuthal gap · Taiwan

---

## Abstract

The earthworm-Based Earthquake Alarm Reporting (eBEAR) system is the operational earthquake early warning (EEW) system of Taiwan's Central Weather Administration (CWA). Offshore earthquakes are the hardest class because the source lies outside the land network and all stations occupy one side of the epicentre. We analyse the 25 August 2026 Taitung offshore earthquake ($M_L$ 5.85, depth 13.1 km, 48 km off southeastern Taiwan) using 83 sequential eBEAR solutions, three dissemination channels and 166 intensity observations. CWA issued its first public alert 13.67 s after origin time on all three channels; 92.5% of stations were warned before intensity 3, and cell broadcast covered 17 counties against an observed intensity-3 footprint of 15.

The first alert reported $M$ 6.6, 0.75 units above the analyst magnitude, and all 166 compared stations were over-warned. Three terms account for the overestimate. First, reported magnitude is a function of assumed hypocentral distance: two solutions from identical $Pd$ amplitudes in the same second differed by 0.89 units because their assumed distances differed, and epicentral error and magnitude correlate at $r=-0.74$. Second, the three stations that set the first magnitude lay on the P-wave radiation maximum ($|F_P|$ 1.78 times the all-azimuth average), predicting $+0.29$ against an observed $+0.28$; PGA follows the theoretical S-wave radiation pattern (exponent 1.13 versus 1.0) with no residual directivity. Third, a $+0.42$ bias persists at the best geometry and recurs in a second offshore event, so offshore paths need a separate magnitude calibration.

Traditional quality indicators fail under this geometry. Azimuthal gap is necessarily large for any correct offshore location and small only when the epicentre is wrongly placed on land, so a gap threshold would block valid offshore alerts. Magnitude error is a poor gate because early landward stations often sample a strong radiation lobe, making an initial overestimate expected rather than diagnostic. We propose gates based on the azimuthal coverage of magnitude stations, so a one-sided sample is not promoted, and on cross-stream location consistency among eBEAR's parallel algorithms, so a solution is released only when independent methods agree.

---

## 1. Introduction

Earthquake early warning (EEW) exploits the interval between the fast, weak P wave and the slower, damaging S wave, so its performance is governed by how quickly and how accurately the source can be characterised from the first seconds of P-wave data (Allen and Melgar 2019). For sources inside a dense network the problem is comparatively benign: near-source stations surround the epicentre, azimuthal coverage is good, and the hypocentre is constrained within seconds. For offshore sources, the dominant hazard class along subduction margins, none of these conditions hold: the nearest station may be tens of kilometres away, all stations occupy a limited azimuthal range on land, and both location and magnitude must be inferred from a one-sided sampling of the wavefield. Operational systems worldwide face this geometry, among them SASMEX in Mexico (Espinosa-Aranda et al. 2009), ShakeAlert on the U.S. West Coast (Given et al. 2018) and the Japan Meteorological Agency system, which adopted the wavefield-based PLUM method precisely to stay robust where source parameters are poorly constrained (Kodera et al. 2016).

Taiwan is an instructive laboratory for this problem. The island sits at the convergent boundary between the Eurasian and Philippine Sea plates (Angelier 1986; Kao and Chen 2000); a large share of its felt earthquakes originate offshore in the Ryukyu and Manila subduction systems, whereas the seismic network is necessarily concentrated on land. The Central Weather Administration (CWA) has operated an EEW system for two decades and has published performance milestones mostly for inland shallow events (Wu and Teng 2002; Hsiao et al. 2009, 2011; Chen et al. 2015, 2019). Figure 1 makes the resulting geometry explicit for the event analysed here. The 25 August 2026 Taitung earthquake ($M_L$ 5.85) occurred 48 km east-southeast of Taitung City, outside the land network, with its nearest station 14 km away on Green Island and every remaining station in a single sector to the west and northwest. An inland earthquake of the same size would be enveloped by stations, the nearest one about 5 km away.

![Figure 1](../figures/manuscript/fig01.png)

**Figure 1.** CWA real-time seismic network and the 25 August 2026 Taitung offshore earthquake. Grey circles: strong-motion stations; blue triangles: velocity/broadband stations, as configured in the eBEAR instance analysed here (551 and 228 stations respectively within the map area). Red star: the epicentre of the analysed event; the beachball, plotted offset and connected by a line to the epicentre, shows the Real-time Moment Tensor (RMT) focal mechanism used in Section 5 (strike 182°, dip 50°, rake 60°; Lee et al. 2014). Epicentres of the three comparison events of Section 6 are listed in Table 5.

Most operational EEW magnitudes derive from the amplitude or period of the first few seconds of the P wave. The peak initial displacement $Pd$, measured over a fixed window of typically 3 s, scales with magnitude and distance and is widely used for real-time magnitude estimation (Wu and Kanamori 2005; Wu and Zhao 2006; Zollo et al. 2006). Three limitations are known: saturation when the window is shorter than the rupture duration (Trugman et al. 2019); strong sensitivity to the assumed hypocentral distance, because the distance-correction term is steep; and station-to-station scatter caused by site response and by the source radiation pattern. The last two interact destructively offshore. The earliest triggering stations occupy a narrow azimuth range, so the magnitude is averaged over a single sector of the focal sphere, while any epicentral error translates directly into a distance error and hence into a magnitude error. To our knowledge these two effects have not previously been separated and quantified in an operational record.

This paper closes that gap using the complete operational record of a moderate offshore earthquake. We document the CWA response report by report, covering all six parallel processing streams and all three public dissemination channels; we decompose the first-alert magnitude bias into a location-distance term, an azimuthal-sampling term and an intrinsic relation term; and we test which physical mechanism controls the azimuthal term, using the focal mechanism of the event. We then ask whether the result generalises, by recomputing identical metrics for three further Taiwan earthquakes spanning offshore and near-coast geometries. The outcome is a set of transferable quality-control conclusions: two indicators in routine use, magnitude error and azimuthal gap, are shown to be invalid on their own for offshore sources, and alternatives based on magnitude-station azimuthal coverage and cross-stream location consistency are proposed. Section 2 describes the system and data, Section 3 the evaluation metrics and analysis protocol, Sections 4 to 6 the results, and Sections 7 and 8 the discussion and conclusions.

---

## 2. System and Data

The Central Weather Administration (CWA) real-time seismic network is a mixed-sensor system that combines velocity and acceleration instruments in surface, borehole and ocean-bottom installations. Velocity sensors provide the sensitivity to weak early P-wave motion that is decisive for offshore sources; accelerometers preserve waveform fidelity under strong shaking without clipping. Data are digitised at 24 bit, packetised at 1 s, and delivered with a typical end-to-end latency of 0.5–2 s. Real-time processing runs within the Earthworm framework (Johnson et al. 1995). By 2025 the national inventory comprised 603 accelerometers, 179 velocity stations and 9 ocean-bottom stations. The operational instance analysed here was configured with 551 strong-motion and 228 velocity/broadband stations inside the map area of Figure 1. Their distribution is dense across the island but, as that figure shows, provides no coverage seaward of the east coast, so the epicentral region itself is unsampled. Every offshore hypocentre must therefore be located and sized from a one-sided, landward sampling of the wavefield.

The earthworm-Based Earthquake Alarm Reporting (eBEAR) system (Chen et al. 2015) runs as multiple parallel instances that share the same real-time data feed but differ in association parameters and location algorithm. Two location families operate simultaneously. The effective-epicentre (geometric-centre) method returns the centroid of triggered stations with depth fixed at 10 km; it is immediate and robust against non-convergence (Chen et al. 2019). The Geiger inversion method solves for the hypocentre iteratively and can resolve depth, but it requires a usable station geometry. For this event, six streams ran in parallel on four computers, two using the geometric-centre method and four using Geiger inversion. Each stream writes one report file (`.rep`) per solution, listing source parameters, station counts $n$ and $n_m$, azimuthal gap, and a per-station table of $Pa$, $Pv$, $Pd$, $M_{Pd}$ and assumed distance $R$, so that the operational magnitude is fully auditable at station level (Section 5). Three magnitudes are computed ($M_{Pd}$, $M_{tc}$ and $M_{all}$); **the disseminated magnitude is $M_{Pd}$**.

Alerts are distributed through three independent channels with different thresholds: (i) the Public Warning System (PWS) cell-broadcast, nominally for $M\geq5.0$ and predicted intensity $\geq3$ (Taipei $\geq2$); (ii) a television channel (CAP), nominally $M\geq5.0$ and predicted intensity $\geq2$; and (iii) a school channel (XML via a dedicated network), nominally $M\geq4.5$ and predicted intensity $\geq2$. The school channel transmits successive updates, whereas PWS and TV normally issue a single message per event. The analysis uses 83 eBEAR solutions (2065 single-station records), the analyst-reviewed P-file with 290 phases and 166 intensity/PGA stations, the issue-sequence log, CAP/XML alert files (1 PWS, 1 TV, 4 school), per-second intensity for 626 stations over 120 s, and the Real-time Moment Tensor (RMT) solution of the Institute of Earth Sciences, Academia Sinica (strike 182°, dip 50°, rake 60°; Lee et al. 2014). Three additional archived events (Section 6) provide the comparison baseline. For every event, reference hypocentre and magnitude are read from that event's analyst-reviewed P-file header so that all events are treated identically.

---

## 3. Evaluation Metrics and Analysis Protocol

The reference (ground truth) is the CWA analyst-reviewed solution. For the Taitung event this is 2026-08-25 07:00:11.33 UTC, 22.6252°N, 121.5968°E, depth 13.05 km, $M_L$ 5.85, based on 290 phases (azimuthal gap 105°, rms 0.11 s, quality grade B) and matching CWA catalogue report No. 115057. Latency of a solution is its reporting time minus the reference origin time. Alert latency is the `sent` timestamp in the CAP or XML product minus that origin time: the instant the product left the warning system, excluding downstream cell-broadcast delivery, which is not recorded here. All events are measured identically, so cross-event comparisons are internally consistent. Epicentral error is the horizontal distance between the solution and the reference epicentre, and magnitude bias is $\Delta M = M_{Pd} - M_L^{\mathrm{ref}}$. A well-located solution has epicentral error below 10 km; the converged value is the median of the last three well-located solutions; the geometry penalty is the earliest well-located magnitude minus that converged value.

Because each report lists $Pd$, assumed hypocentral distance $R$ and single-station $M_{Pd}$, the operational magnitude is fully specified at station level and can be recovered by least squares over all 2065 single-station records of the event: $M_{Pd} = 4.79 + 1.16\,\log_{10}(Pd) + 1.85\,\log_{10}(R)$, with $Pd$ in cm, $R$ in km and rms 0.13. Predicted and reported values lie on the 1:1 line (Fig. 8d), confirming that reported magnitude is a deterministic function of $Pd$ and assumed distance, not an independent estimate. The coefficient 1.85 on $\log_{10}R$ is steep: a factor-of-two error in assumed distance produces 0.56 magnitude units of error, so any offshore mislocation toward the land network maps directly into a magnitude bias. Event magnitude is the mean of the station values used in each report; therefore two solutions computed from identical $Pd$ amplitudes can differ only through their assumed distances. The recovered relation is used only as a diagnostic description of this operational implementation, not as a proposed new scaling law.

Far-field P- and S-wave radiation coefficients $F_P$, $F_{SV}$ and $F_{SH}$ are computed from the Real-time Moment Tensor (RMT) focal mechanism (Lee et al. 2014) following Aki and Richards (2002, Box 4.4), with take-off angle measured from the downward vertical. Take-off angles for the 166 analyst-reviewed stations come from the P-file; for report-file stations they are interpolated from the P-file distance–take-off relation. Because observed amplitudes never vanish on nodal planes, $|F|$ is floored at 0.10. We use $|F_S|=\sqrt{F_{SV}^2+F_{SH}^2}$ against PGA and $|F_P|$ against $Pd$. Coefficient uncertainties are estimated by bootstrap resampling (4000 iterations); significance of an azimuthal or radiation term is assessed by permutation (4000 iterations). Azimuthal structure is the amplitude $\sqrt{b^2+c^2}$ of the best-fitting one-cycle harmonic $y=a+b\cos\phi+c\sin\phi$. Four events with complete report archives are compared in Section 6: all metrics are recomputed from the raw report files and each event's own analyst P-file using identical code, so the offshore versus near-coast contrast is not affected by catalogue convention.

---

## 4. The 25 August 2026 Taitung Offshore Earthquake

The earthquake occurred at 15:00:11.33 local time (07:00:11.33 UTC) 48 km east-southeast of Taitung City at 13.1 km depth, with $M_L$ 5.85. It is reverse-faulting with a small strike-slip component (strike 182°, dip 50°, rake 60°; Lee et al. 2014), the P axis nearly horizontal at azimuth 293°. The nearest station, on Green Island (LDU, 14.1 km), recorded 150.1 gal and intensity 4, the largest ground motion of the event. Of the 166 analyst-reviewed stations, 6 reached intensity 4, 13 reached intensity 3, and the rest intensity 2 or below. All three channels issued their first message at 07:00:25 UTC, 13.67 s after origin time; the first internal solution was available at 12.52 s. PWS covered 17 counties, television 11, and the school channel 12 at predicted intensity $\geq 3$, with three later updates (Fig. 2, Table 1). Fifteen counties eventually recorded intensity 3 or above, so PWS coverage exceeded the observed footprint: the alert was conservative rather than under-inclusive (Fig. 3).

![Figure 2](../figures/manuscript/fig02.png)

**Figure 2.** PWS coverage of the first alert (17 counties, shaded) with the epicentre (star) and dashed circles showing the S-wave response-time contours at 10 s intervals from the alert instant. The 0 s contour marks the theoretical blind zone boundary.

| Channel | Messages | First alert (s) | Coverage |
| --- | ---: | ---: | --- |
| PWS (cell broadcast) | 1 | 13.67 | 17 counties/cities |
| Television (CAP) | 1 | 13.67 | 11 counties/cities |
| School (XML) | 4 | 13.67 | 12 counties at predicted intensity ≥ 3 |

**Table 1.** Dissemination summary. The three channels dispatched simultaneously; the entire alert delay is therefore upstream of the publication pipeline.

![Figure 3](../figures/manuscript/fig03.png)

**Figure 3.** Cumulative number of alerted counties for the three channels compared with the observed cumulative count of counties first exceeding intensity 3 (per-second intensity data). All channels reach their final coverage at 13.7 s, whereas the observed footprint grows until about 65 s. The first county exceeded intensity 3 at about 4 s, before any alert was issued.

Eighty-three solutions were produced by six streams within 40 s. Location convergence was rapid for the Geiger streams and poor for the geometric-centre streams: one Geiger stream was within 4.6 km of the reference in its first solution at 12.5 s, whereas a geometric-centre stream placed the epicentre 35.4 km inland and never recovered (final error 36.1 km). Final errors for the four converging streams were 0.8–1.9 km. Magnitude stabilised at 6.1–6.4 against the reference 5.85; depth remained at the 10/20/30 km grid nodes (Figs. 4, 5). Compared with the 166 analyst-reviewed observations, the first school report ($M$ 6.6 at 30 km) was exact at 10.2% of stations and within $\pm 1$ intensity rank at 59.0%; later reports reached 80.7% within $\pm 1$ (Table 2). First-report residuals are entirely non-negative: no station was under-warned, and most were over-warned by one to two ranks (Fig. 6). Accuracy improved with each update, but the message that reached the public was the least accurate one.

![Figure 4](../figures/manuscript/fig04.png)

**Figure 4.** Epicentre convergence trajectories of the six parallel streams. The reference epicentre is the yellow star. Early geometric-centre solutions lie on land, 35–43 km northwest of the true offshore source.

![Figure 5](../figures/manuscript/fig05.png)

**Figure 5.** Evolution of (a) magnitude, (b) horizontal location error, (c) depth and (d) station count versus latency for the six streams. Magnitude stabilises at 6.1–6.4 against the reference 5.85; depth remains at the 10/20/30 km grid nodes.

| Report | Magnitude / depth | Exact (%) | Within ±1 (%) |
| --- | --- | ---: | ---: |
| 1 (13.67 s) | $M$ 6.6 / 30 km | 10.2 | **59.0** |
| 2 (14.67 s) | $M$ 5.9 / 20 km | 27.1 | 75.9 |
| 3 (14.67 s) | $M$ 6.1 / 20 km | 24.7 | 75.9 |
| 4 (17.67 s) | $M$ 5.9 / 20 km | 37.4 | 80.7 |

**Table 2.** Intensity prediction accuracy per school-channel report (166 compared stations).

![Figure 6](../figures/manuscript/fig06.png)

**Figure 6.** Intensity residual (predicted minus observed) distributions for the first and second reports. The first report is entirely non-negative.

Using the per-second observed intensity of 626 stations, the first issued solution preceded the S-wave arrival at 99.0% of stations (median lead 33.6 s) and preceded the crossing of intensity 3 at 92.5% of stations that eventually reached intensity 3 (median lead 29.1 s). Taitung City, 48.7 km from the epicentre, had a theoretical lead of only 2.1 s relative to the 13.67 s alert; Green Island and the Taitung coast exceeded intensity 4–5 within 4–13 s, before the alert was issued (Fig. 7). The blind-zone population is small, but the geometry is intrinsic: for an offshore source the closest exposed community is also the least protected. The disseminated solution reported $M_{Pd}$ 6.58; the same report contained $M_{tc}$ 7.63 and $M_{all}$ 7.10. Because CWA disseminates $M_{Pd}$, the public alert was $M$ 6.6 rather than $M$ 7.1. $M_{tc}$ reached 8.5 in three early solutions, confirming the operational value of restricting dissemination to the more stable amplitude-based magnitude in the first seconds.

![Figure 7](../figures/manuscript/fig07.png)

**Figure 7.** Per-second maximum observed intensity by latitude band, with the alert times superimposed. Intensity 5 is reached in the 22.6°N band within about 4 s, well before the first alert at 13.7 s.

---

## 5. Magnitude Bias: Decomposition and Mechanism

Reported magnitude tracks assumed distance. At 07:00:23.8 UTC two streams produced solutions in the same second from the same stations with identical $Pd$ values; their only difference was the assumed hypocentre (Table 3). The Geiger solution reported 6.55, the geometric-centre solution 5.66. The 0.89-unit difference equals $1.85\log_{10}(60/21)=0.84$ predicted by the operational relation. The solution that appeared accurate ($M$ 5.66 against $M_L$ 5.85) was the badly mislocated one (35.4 km error), while the correctly located solution (4.6 km error) over-estimated. Within a geometric-centre stream the same coupling appears: when it briefly converged to within 1.1 km, magnitude jumped from 5.46 to 6.42, then fell to 5.81 as the epicentre drifted inland. Over all 83 solutions, epicentral error and reported magnitude correlate at $r=-0.74$, with a slope of $-0.15$ units per 10 km of location error (Fig. 8). The regression crosses the reference magnitude at an epicentral error of about 30 km: the apparently most accurate magnitudes were produced by solutions mislocated by 30 km.

| Station | $Pd$ (cm) | Geiger $R$ (km) | Geiger $M_{Pd}$ | Centroid $R$ (km) | Centroid $M_{Pd}$ |
| --- | ---: | ---: | ---: | ---: | ---: |
| G035 | 0.06748 | 55 | 6.63 | 15 | 5.66 |
| G036 | 0.06561 | 54 | 6.59 | 16 | 5.67 |
| G047 | 0.04337 | 60 | 6.45 | 21 | 5.64 |
| G046 | 0.02910 | 60 | 6.23 | 21 | 5.43 |
| **Event magnitude** | | | **6.55** | | **5.66** |

**Table 3.** Identical amplitudes, different assumed distances. The 0.89-unit difference equals $1.85\log_{10}(60/21)=0.84$ predicted by the operational relation.

![Figure 8](../figures/manuscript/fig08.png)

**Figure 8.** Evidence that reported magnitude tracks assumed distance. (a) Two solutions computed in the same second from identical $Pd$ values. (b) Magnitude and location error report by report for a geometric-centre stream. (c) All 83 solutions, $r=-0.74$. (d) Recovered operational relation, 2065 single-station records, rms 0.13.

The first disseminated solution used only three magnitude stations at azimuths 295–307° from the epicentre, a 12° sector. The nearest station, LDU (14.1 km, azimuth 292°), recorded $Pa$ = 162.3 gal but $Pd$ = 0.0006 cm, yielding magnitude 3.46 — an integration or saturation failure at the one station that could have anchored the estimate downward. Among 72 single-station magnitudes of the final well-located solution, estimates vary by 0.3–0.5 units between sectors at the same distance; the west-northwest sector used by the first report ($<$ 60 km) is the highest (median 6.54). Stations beyond 150 km yield 5.4–5.9 but join only after the eleventh report. Azimuthal gap is a weak predictor when the location is correct ($r=0.23$) and only matters at the extreme ($>$ 300°, $n_m\leq4$). Among poorly located solutions the correlation is strong ($r=0.76$) but spurious: the six smallest-gap solutions (125–139°) are the six worst-located (mean 41 km), because an inland epicentre artificially improves apparent coverage (Fig. 9).

![Figure 9](../figures/manuscript/fig09.png)

**Figure 9.** Azimuthal evidence. (a) Station azimuth coverage: no station exists between 45° and 180°; red lines mark the three stations that set the first magnitude. (b) Median single-station magnitude by azimuth sector and distance band. (c) Azimuth versus single-station magnitude residual for the final solution. (d) Direction of the strongest distance-corrected observed PGA per distance band.

The RMT mechanism (Lee et al. 2014) places the P axis (azimuth 293°, plunge 1°) on the first-report stations. Their mean $|F_P|$ is 0.699 against an all-azimuth average of 0.392, a ratio of 1.78 that predicts $+0.29$ magnitude units (Table 4). Observed PGA follows the theoretical S-wave radiation pattern with exponent $+1.13$ (theoretical 1.0; $p<0.001$); after removing distance and radiation, the residual azimuthal harmonic is 0.028 ($p=0.92$), so no rupture-directivity signal remains (Fig. 10). The predicted $+0.29$ matches the $+0.28$ geometry penalty measured as a well-located Geiger stream improved from three magnitude stations to thirty-two. That stream reported 6.55 at first and converged to 6.30, not to the analyst $M_L$ 5.85. The first-alert budget is therefore $5.85 + 0.42$ ($Pd$ relation) $+ 0.28$ (one-sided sampling) $= 6.55$ (Fig. 11). The $+0.42$ residual persists at the best geometry the event achieved and is a property of the $Pd$ relation for this offshore path; improving the network cannot remove it, only calibration can.

| Station | Azimuth | Take-off | $|F_P|$ |
| --- | ---: | ---: | ---: |
| G036 | 295° | 68° | 0.748 |
| G047 | 297° | 70° | 0.790 |
| G035 | 307° | 65° | 0.559 |
| **Mean of the three** | | | **0.699** |
| Network median (72 stations) | | | 0.447 |
| All-azimuth average | | | 0.392 |

**Table 4.** The three stations that set the first magnitude sat on the maximum lobe of the P-wave radiation pattern. The ratio 0.699/0.392 = 1.78 predicts a magnitude bias of $1.16\log_{10}(1.78)=+0.29$.

![Figure 10](../figures/manuscript/fig10.png)

**Figure 10.** Radiation pattern and the magnitude stations. (a) Lower-hemisphere P-wave radiation pattern with the 166 analyst-reviewed stations (grey) and the three first-report stations (red stars, with $|F_P|$); the stars lie adjacent to the P axis. (b) $|F_P|$ and $|F_S|$ versus azimuth; outer ticks are station azimuths, showing the empty 45–180° sector. (c) Distance-corrected observed PGA versus theoretical $|F_S|$, slope $+1.11$ (multivariate $+1.13$). (d) Azimuthal residuals before and after removing the radiation pattern.

![Figure 11](../figures/manuscript/fig11.png)

**Figure 11.** Error budget of the first alert. The +0.42 term is independent of station geometry; the +0.28 term is the azimuthal-sampling penalty, quantitatively explained by the radiation pattern (+0.29 predicted).

## 6. Cross-Event Comparison

To test whether the offshore bias is event-specific, we recomputed all metrics for three further Taiwan events with complete report archives, using each event's own analyst P-file as reference and identical code, so that catalogue convention cannot explain the contrast (Table 5). Besides the Taitung 2026 offshore $M_L$ 5.85 shock (nearest station 14.1 km; 83 solutions), the set comprises the deep offshore Yilan 2025 $M_L$ 7.01 event (67.7 km depth; nearest station 15.8 km; 104 solutions), the near-coast Hualien 2026a $M_L$ 5.74 event (nearest station 5.0 km; 81 solutions) and the inland Hualien 2026b $M_L$ 5.01 event (nearest station 5.2 km; 67 solutions). First public alert is the earliest `sent` timestamp among the three channels. For Taitung and Yilan all channels dispatched simultaneously; for Hualien 2026b the school channel led at 8.26 s and PWS followed at 17.26 s. The comparison is a case-controlled contrast of two sources outside the network against two at its edge or inside it.

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

Three patterns emerge (Fig. 12). The magnitude bias is a property of offshore geometry, not of the system. Both offshore events over-estimate among well-located solutions ($+0.38\pm0.17$ and $+0.45\pm0.14$); both near-coast events, whose nearest station is about 5 km away, are unbiased ($-0.08\pm0.17$ and $-0.07\pm0.16$). The discriminating variable is the distance to the nearest station, that is, whether the source lies inside or outside the network (Fig. 12a). Yilan is deep and larger than Taitung, yet the over-estimate has the same sign. The mislocation–magnitude compensation is likewise specific to offshore sources. Only Taitung and Yilan show negative correlation between epicentral error and reported magnitude ($r=-0.74$ and $-0.55$), because their mislocations are systematically directed toward the network. The two Hualien events, whose mislocations are unsystematic, show weak positive correlations ($r=+0.23$ and $+0.46$; Fig. 12c). First-report intensity within $\pm1$ is 59.0% for Taitung against 88.1, 92.6 and 92.4% for the other three events, consistent with the larger first-alert over-estimate of the Taitung case.

![Figure 12](../figures/manuscript/fig12.png)

**Figure 12.** Cross-event comparison. (a) Magnitude bias of well-located solutions versus the distance to the nearest station. (b) First internal solution and first public alert latency. (c) Correlation between epicentral error and reported magnitude. (d) Magnitude bias versus latency for well-located solutions only.

Offshore geometry also costs 4–6 s of alert latency, consistently: first internal solutions at 12.5–14.1 s and first public alerts at 13.7 s for the two offshore events, versus 7.9–8.0 s internal and 8.3 s public for the two near-coast events (Fig. 12b). Stations warned before intensity 3 remain high for Taitung, Yilan and Hualien 2026a (92.5, 82.6 and 92.5%), whereas Hualien 2026b falls to 64.2% because that smaller inland shock produced a smaller intensity-3 footprint. Four events cannot establish a population statistic; the design is a case-controlled contrast intended to test whether the Taitung mechanism generalises within Taiwan's own operational record. It does so at the level of sign and of latency, not of a transferable numerical correction: the two offshore residuals differ, Yilan is much deeper than Taitung, and the near-coast pair is unbiased despite sharing the same processing system. A larger offshore sample would be required before an operational correction of $-0.3$ to $-0.4$ is deployed.

## 7. Discussion

The three bias terms act together offshore and in different directions inland. Offshore mislocation is systematically toward the land network, so it lowers the assumed distance and therefore the magnitude; any location improvement then raises the magnitude. Inland mislocations have no preferred direction, so the distance term averages out (Table 5). The earliest offshore stations occupy one sector of the focal sphere, and whether the magnitude is biased high or low is set by where that sector falls on the radiation pattern. Here it fell on the P-axis lobe ($+0.29$); a nodal sample (azimuth 210°, $|F_P|=0.01$) would have under-estimated, with a risk of missed warning. The persistent $+0.42$ for Taitung and $+0.45$ for Yilan indicates that the operational $Pd$ scaling, calibrated mainly on inland paths, over-predicts for offshore paths. The sign of the initial bias is not universal: the near-coast events start below the reference and rise toward it, whereas Taitung starts above and falls toward a biased plateau (Fig. 12d).

Magnitude error alone is not a valid quality metric. In the Taitung event the absolute magnitude error of the poorly located solutions (mean 0.21) was smaller than that of the well located solutions (0.38), because distance under-estimation cancelled the relation bias. Ranking by magnitude error would therefore select the worst solutions; location and magnitude error must be reported as a pair. Azimuthal gap is similarly misleading offshore: a correct offshore solution necessarily has a large gap (minimum 100° here), whereas an incorrect inland placement acquires a small gap, and the six smallest-gap solutions were the six worst-located. Operators should apply an offshore-specific magnitude correction (here $-0.3$ to $-0.4$), require a minimum magnitude-station count and azimuthal spread before public dissemination, detect $Pd$ integration failures at near-source high-gain stations in real time, and use cross-stream location consistency rather than gap as the promotion gate. Preferring $Pd$ over $\tau_c$ in the first seconds, and a median of station magnitudes, further limits early outliers.

| Priority | Recommendation | Evidence |
| --- | --- | --- |
| High | Apply an offshore-specific magnitude correction (here $-0.3$ to $-0.4$), validated on additional events before deployment | $+0.38$ and $+0.45$ residual bias in two offshore events at the best achievable geometry |
| High | Require a minimum magnitude-station count and azimuthal spread (e.g. $n_m\geq5$ spanning ≥ 2 quadrants) before promoting a magnitude to public dissemination | $n_m\leq4$ solutions have $\Delta M$ scatter 0.41 versus 0.23 for $n_m\geq5$; first alert used $n_m=3$ within a 12° sector |
| High | Detect and repair $Pd$ integration/saturation failures at near-source high-gain stations in real time | LDU recorded 162 gal but returned $Pd$ = 0.0006 cm, removing the only near-source constraint |
| Medium | Use cross-stream location consistency (e.g. two independent streams within 15 km) as the promotion gate instead of gap | At 07:00:24 two streams on the same computer differed by 35 km, a detectable inconsistency |
| Medium | Report location error and magnitude error jointly in verification | Poorly located solutions had smaller magnitude error than well-located ones |
| Medium | Prefer the amplitude-based magnitude over $\tau_c$-based or combined magnitudes in the first seconds | $M_{tc}$ reached 8.5; $M_{all}$ would have produced $M$ 7.1 instead of $M$ 6.6 |
| Medium | Use median or trimmed-mean station magnitude rather than the mean of a few stations | With three stations, a single 0.5-unit outlier shifts the event magnitude by 0.17 |

Three aspects of the CWA implementation performed well. Parallel geometric-centre and Geiger streams supplied both immediate solutions and the only accurate offshore locations; simultaneous PWS, television and school dispatch meant that the entire 13.67 s was source-estimation time; and PWS coverage of 17 counties against an observed intensity-3 footprint of 15 produced over-alerting rather than missed alerting, the preferable failure direction, although repeated over-alerting carries a long-term cost in public credibility. The mechanism analysis nevertheless rests on a single event and a single focal mechanism; azimuths between 45° and 180° contain no stations, so an east-southeast directivity lobe could not be detected; site response is not modelled separately; four events cannot establish a population statistic; and the recovered $Pd$ coefficients describe this operational implementation only. Where a mechanism is available within seconds, weighting station magnitudes by the theoretical radiation coefficient would remove the sampling term directly; otherwise azimuthal-spread requirements achieve much of the same effect, because the four-lobed pattern averages out over quadrants.

## 8. Conclusions

We analysed the complete operational record of the 25 August 2026 Taitung offshore $M_L$ 5.85 earthquake: 83 eBEAR solutions from six parallel streams, three dissemination channels, 166 analyst-reviewed intensity observations and per-second intensity for 626 stations. Operationally the system performed as designed for an offshore source. The first public alert was issued 13.67 s after origin time simultaneously on all three channels; 92.5% of stations that reached intensity 3 were warned beforehand, with a median lead of 29.1 s; PWS coverage of 17 counties exceeded the observed intensity-3 footprint of 15. The blind zone was confined to Green Island, the Taitung coast and Taitung City, where theoretical lead was only 2.1 s. Because CWA disseminates $Pd$ rather than $\tau_c$ or the combined magnitude, the public message was $M$ 6.6 rather than $M$ 7.1. Geometric-centre streams provided immediate inland solutions; Geiger streams provided the only accurate offshore locations. The remaining problem is not missed warning but a systematic over-estimate of magnitude and intensity.

The first alert over-estimated magnitude by 0.75 units, and the bias decomposes cleanly. A $+0.42$ term arises from the $Pd$ scaling relation itself and survives at the best achievable geometry; a $+0.28$ term arises from one-sided azimuthal sampling. Two solutions computed in the same second from identical $Pd$ amplitudes differed by 0.89 units because their assumed distances differed, and over all 83 solutions epicentral error and reported magnitude correlate at $r=-0.74$. The sampling term is controlled by the source radiation pattern. The three stations that set the first magnitude lay on the P-wave maximum lobe of the RMT mechanism (Lee et al. 2014), with $|F_P|$ 1.78 times the all-azimuth average, predicting $+0.29$ against an observed $+0.28$. Observed PGA follows the theoretical S-wave radiation pattern with exponent 1.13 (theoretical 1.0), and no residual azimuthal signal remains, excluding rupture directivity. The same offshore over-estimate recurs for the deep Yilan event ($+0.45$ among well-located solutions), whereas two near-coast events are unbiased.

Two widely used quality indicators fail for offshore sources. Magnitude error alone selects the worst-located solutions, because mislocation toward the network compensates the relation bias; azimuthal gap alone rewards solutions incorrectly placed inside the network. For subduction-margin EEW operators the practical implications are to calibrate magnitude separately for offshore paths (here $-0.3$ to $-0.4$, pending a larger sample), to gate dissemination on the number and azimuthal spread of magnitude stations rather than on gap, to verify location and magnitude jointly, to use cross-stream location consistency as a promotion check, and to monitor near-source high-gain channels for $Pd$ integration failures. Preferring the amplitude-based magnitude in the first seconds, and a median of station magnitudes, further limits early outliers. These measures are inexpensive relative to network expansion and address the dominant error terms identified here. Four events are a case-controlled contrast, not a population statistic; the radiation-pattern control is demonstrated for this geometry, not claimed as a universal rule.

---

## Declarations

**Funding** [TODO: grant numbers and funding bodies, or state that no funding was received.]

**Competing interests** The authors declare no competing interests.

**Ethics approval** Not applicable.

**Consent to participate / Consent for publication** Not applicable.

**Data availability** The eBEAR operation logs (83 report files for the Taitung event and 252 for the three comparison events), the analyst-reviewed P-files, the alert products (`CWA-EEW115006201`-`204` and the corresponding PWS and TV CAP files) and the per-second intensity files are maintained by the Central Weather Administration and are available from the corresponding author on reasonable request. The focal mechanism is from the Real-time Moment Tensor Monitoring System of the Institute of Earth Sciences, Academia Sinica (https://rmt.earth.sinica.edu.tw/; Lee et al. 2014). Derived data tables underlying every figure are provided as supplementary material.

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

Lee SJ, Liu Q, Tromp J, Komatitsch D, Liang WT, Huang BS (2014) Toward real-time regional earthquake simulation II: Real-time Online earthquake Simulation (ROS) of Taiwan earthquakes. J Asian Earth Sci 87:56-68. https://doi.org/10.1016/j.jseaes.2014.02.009

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
5. Confirm the journal's current abstract word limit (this abstract is about 330 words) and keyword count (six are supplied).
6. Verify the reference style against the current Acta Geophysica guide for authors; the list below follows the Springer basic author-date style with abbreviated journal titles.
7. Add DOIs to all references where available.
8. Supplementary material: the per-report data tables (`cross_event_summary.csv`, `magnitude_relations.csv`, `radiation_pattern_stations.csv`) are candidates for deposition.
