# RA Task - Ohio Highway Resurfacing Data Collection Project

## Overview

This codebase completes a comprehensive data collection task as specified in `RA_Task.pdf`. While the original project requirements called for analyzing 5 projects, the scope has been expanded to include all 202 available projects in the dataset to demonstrate thoroughness and technical proficiency. Additionally, supplementary columns have been generated to ensure data completeness and enhance analytical value, which include bidder location, bidder bid amount, and bid success status. 

## Project Methodology

The following section outlines the systematic approach used to complete this data collection task:

### Phase 1: Data Understanding and Exploration (`1.ipynb`)
- **Objective**: Comprehensive dataset analysis and column interpretation
- **Activities**:
  - Documented the meaning and properties of each column
  - Analyzed relationships between variables
  - Conducted summary statistics analysis
  - Identified missing and unique values
  - Developed a strategic framework for data extraction
  - Researched relevant data sources and websites

### Phase 2: Automated County and Route Information Extraction (`2.ipynb`)
- **Objective**: Systematically extract geographical and route data
- **Process**:
  - Implemented automated search functionality using the TIMS website
  - Extracted county and route information for all projects
  - Generated FIPS codes using county and state information
  - Prioritized "Recorded County" data for consistency over alternative county measures

### Phase 3: Error Handling and Data Validation (`3.ipynb` and `4.ipynb`)
- **Objective**: Address data quality issues identified in Phase 2
- **Challenges Addressed**:
  - Resolved instances where counties were marked as "District" instead of actual county names
  - Implemented fallback to "Work County" when "Recorded County" was unavailable
  - **Data Quality Note**: While "Work County" is less consistent than "Recorded County", this substitution affects only a small portion of the dataset and maintains overall data integrity

### Phase 4: Comprehensive Data Enhancement (`5.ipynb`)
- **Objective**: Populate dataset with critical project metrics
- **Data Elements Added**:
  - Number of lanes
  - Project duration
  - Winning bid amounts
  - Actual project costs
- **Quality Assurance**:
  - Conducted summary statistics analysis
  - Performed data validation checks
  - Generated visualizations to verify data reasonableness

### Phase 5: PDF Document Processing (`6.ipynb`)
- **Objective**: Download and process project documentation
- **Process**:
  - Downloaded project proposal and bid tabulation PDFs
  - Prepared documents for engineering estimate extraction.
  - Extracted bidder lists and count information

### Phase 6: PDF Data Extraction (`7.ipynb`)
- **Objective**: Process downloaded PDFs for data extraction
- **Activities**:
  - Processed PDFs downloaded in Phase 5
  - Implemented data quality consistency checks for error detection
  - Validated extracted information for accuracy

### Phase 7: Bid Tabulation Analysis (`8.ipynb`)
- **Objective**: Extract comprehensive bidder information from bid tabulation documents
- **Data Elements Extracted**:
  - Bidder names and addresses
  - Bidder locations
  - Bid amounts
  - Project award status
- **Output**: `final_output_2.csv`
- **Note**: Due to time constraints and task scope, accuracy verification of this extended dataset was not performed

### Phase 8: Data Validation and Visualization (`9.ipynb`)
- **Objective**: Conduct comprehensive dataset validation and generate insights
- **Activities**:
  - Created visualizations to study dataset validity
  - Generated analytical insights from collected data
  - Performed statistical analysis for data verification

### Phase 9: Error Correction (`10.ipynb`)
- **Objective**: Address minor dataset errors identified during validation
- **Process**: Implemented targeted corrections to improve data quality

### Phase 10: Mileage Analysis (`11.ipynb`)
- **Objective**: Determine appropriate mileage measurement methodology
- **Analysis**:
  - Studied properties of "project length" vs. "work length" measurements
  - Evaluated whether these metrics are interchangeable
  - Concluded that "project length" is most applicable based on mileage definition requirements

### Phase 11: Debugging and Error Resolution (`12.ipynb` and `13.ipynb`)
- **Objective**: Systematic error identification and resolution
- **Process**:
  - Conducted thorough debugging of data extraction processes
  - Identified and resolved all error sources
  - Completed mileage entries for all available projects
- **Findings**: 40 out of 203 projects have officially documented "NA" (not available) project lengths as stated in project proposals

### Phase 12: Data Finalization (`14.ipynb`)
- **Objective**: Final data cleaning and output formatting
- **Activities**:
  - Removed unnecessary columns
  - Standardized data types to match requirements
  - Generated two output formats:
    1. Template-matching layout file
    2. Fields-specific file as requested in `RA_Task.pdf`

## Key Deliverables

### Output Files
- **`final_output_complete.csv`**: Complete dataset containing all extracted fields and enhanced data elements
- **`final_output_specific.csv`**: Targeted dataset with specific fields matching RA_Task.pdf requirements
- **`final_output_2.csv`**: Extended bidder information dataset with comprehensive contractor details

### Documentation
- **`readme.md`**: Comprehensive project documentation and methodology overview
- **Individual Jupyter notebooks (`1.ipynb` through `14.ipynb`)**: Detailed implementation and analysis for each project phase

## Technical Implementation

### Data Sources
- **Primary Dataset**: `Ohio_2018_Resurfacing PRR.xlsx` - Core highway resurfacing project database
- **TIMS Website**: Automated extraction of county and route information through web scraping
- **Project Documentation**: Downloaded proposal and bid tabulation PDFs for detailed project analysis

### Methodology Highlights
- Automated web scraping for geographical data acquisition
- Advanced PDF processing and text extraction techniques
- Statistical validation and comprehensive quality assurance
- Robust error handling and fallback mechanisms
- Systematic data enhancement and validation workflows

## Data Quality Observations and Findings

### Mileage Calculation Methodology Review
A significant data quality consideration has been identified regarding mileage calculation standards:

**Identified Issue**: The provided reference example indicates a two-lane resurfacing project with recorded mileage of 12.982 miles, which may require methodological clarification.

**Supporting Evidence**:
- Project proposal documentation specifies a project length of 6.6490 miles
- Edge line measurement documentation records 12.98 miles
- Industry standard calculation for two-lane roadways typically defines project length as equivalent to half of the total edge line measurement

**Recommendation**: The mileage calculation methodology should be reviewed and standardized to ensure consistent and accurate project scope representation across all dataset entries.