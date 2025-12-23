# CircadianMedicine_AppleHealth

A comprehensive data analysis pipeline for extracting, processing, and visualizing Apple Health data with a focus on circadian rhythm patterns, sleep quality, and activity metrics.

## Overview

This project transforms Apple Health export data into actionable insights for circadian biology research and personal health optimization. It provides detailed visualizations of sleep architecture, activity patterns, and physiological metrics across 24-hour cycles.

## Features

### 📊 Data Extraction & Processing
- **XML Parsing**: Efficiently parses large Apple Health XML exports (50MB+) using streaming methods
- **Multiple Data Sources**:
  - `export.xml`: Health records, workouts, activity summaries
  - `export_cda.xml`: Clinical Document Architecture format with vital signs
- **Data Formats**: Exports to pickle, JSON, and CSV for flexible analysis

### 😴 Sleep Analysis
- **Sleep Stage Detection**: Deep, Core, REM, Awake, and In Bed stages
- **Detailed Metrics**:
  - Nightly sleep duration and composition
  - Sleep efficiency calculations
  - Bedtime and wake time patterns
  - Breathing disturbances during sleep
- **Visualizations**:
  - Hypnograms (sleep stage timelines)
  - Sleep duration trends
  - Sleep composition pie charts
  - Sleep timing patterns across days

### 🏃 Activity Metrics
- **Heart Rate**: Continuous monitoring with normalized ranges (40-180 bpm)
- **Steps**: Step count tracking per measurement period
- **Active Energy**: Calories burned through activity
- **Physical Effort**: Subjective exertion ratings (0-10 scale)
- **Combined Timeline**: 24-hour visualization of all activity metrics alongside sleep

### 📈 Advanced Visualizations
- **24-Hour Timeline Views**: Date-by-date comparison with time of day on x-axis
- **Multi-Metric Dashboards**: Separated or combined activity metrics
- **Color-Coded Intensity**: Visual representation of metric intensities
- **Circadian Pattern Analysis**: Identify patterns across sleep-wake cycles

## Data Types Supported

### Health Metrics (HKQuantityType)
- Heart Rate
- Step Count
- Active Energy Burned
- Physical Effort
- Resting Heart Rate
- Heart Rate Variability
- And 100+ other health metrics

### Categories (HKCategoryType)
- Sleep Analysis with detailed stages
- Apple Stand Hours
- Audio Exposure Events
- Mindful Sessions
- Symptom tracking (chest pain, shortness of breath, etc.)

### Workouts & Routes
- Workout summaries with duration and energy
- GPS routes (`.gpx` files)

### Clinical Records
- Vital signs and observations
- Clinical metadata from CDA format

## Project Structure

```
CircadianMedicine_AppleHealth/
├── import.ipynb              # Main analysis notebook
├── data/
│   └── apple_health_export/
│       ├── export.xml        # Main health data export
│       ├── export_cda.xml    # Clinical document export
│       ├── electrocardiograms/  # ECG recordings
│       └── workout-routes/      # GPS workout data
├── output/                   # Generated analysis files
│   ├── export_data.pkl       # Parsed health records
│   ├── cda_data.pkl         # Parsed clinical data
│   ├── health_records.csv    # CSV export
│   └── sleep_data.csv       # Sleep analysis results
└── README.md
```

## Getting Started

### Prerequisites
```bash
# Python 3.8+
pip install pandas numpy matplotlib seaborn
```

### Usage

1. **Export Apple Health Data**:
   - Open Health app on iPhone
   - Tap profile picture → Export All Health Data
   - Share the ZIP file to your computer
   - Extract to `data/apple_health_export/`

2. **Run Analysis**:
   - Open `import.ipynb` in Jupyter Notebook or VS Code
   - Execute cells sequentially to:
     - Parse XML data
     - Extract sleep and activity metrics
     - Generate visualizations

3. **Explore Results**:
   - View generated CSV files in output directory
   - Analyze visualizations in notebook
   - Customize date ranges and metrics as needed

## Key Insights

The analysis provides:
- **Sleep Quality**: Track sleep stages, duration, and consistency
- **Circadian Patterns**: Identify your natural sleep-wake rhythms
- **Activity Trends**: Understand when you're most active during the day
- **Health Correlations**: See relationships between sleep, activity, and heart rate
- **Personal Baselines**: Establish normal ranges for your metrics

## Example Visualizations

- **Hypnogram**: Detailed sleep stage progression throughout the night
- **24-Hour Timeline**: Sleep stages and activity metrics across multiple days
- **Sleep Duration Trends**: Daily sleep totals with component breakdown
- **Activity Heatmap**: When you're most active during waking hours

## Technical Details

### Memory-Efficient XML Parsing
Uses `iterparse()` to handle large XML files without loading entire document into memory.

### Timezone Handling
Properly manages timezone-aware datetime objects for accurate time-of-day analysis.

### Data Normalization
Scales different metrics to comparable ranges for combined visualizations.

## Limitations

- Off-wrist detection data is not included in Apple Health exports
- Some metrics require specific Apple Watch models or iOS versions
- Historical data availability depends on device usage patterns

## Future Enhancements

- [ ] Interactive dashboards with Plotly/Dash
- [ ] Statistical analysis of circadian rhythm stability
- [ ] Correlation analysis between sleep quality and activity
- [ ] Machine learning predictions for optimal sleep/wake times
- [ ] Export reports in PDF format
- [ ] Integration with other health data sources

## Contributing

Contributions are welcome! Areas for improvement:
- Additional visualization types
- Statistical analysis functions
- Data validation and quality checks
- Performance optimizations
- Documentation and examples

## License

See [LICENSE](LICENSE) file for details.

## Acknowledgments

Built for circadian medicine research and personal health optimization. Inspired by the growing field of precision chronobiology and personalized health analytics.
