# Reddit Business Search Workflow Screenshots

This directory contains all the configuration screenshots for the Reddit Business Search n8n workflow.

## Complete Workflow Screenshots

### Main Workflow Views
- `complete-workflow.png` - Complete workflow overview showing all nodes and connections
- `workflow-overview.png` - High-level workflow diagram showing the four main stages

## Node Configuration Screenshots

### Trigger Nodes
- `manual-trigger-config.png` - Manual trigger configuration for testing

### Data Acquisition
- `reddit-api-config.png` - Reddit API configuration for post retrieval

### Filtering Nodes
- `filter-posts-by-content-config.png` - Content-based filtering configuration
- `filter-features-config.png` - Feature-based filtering configuration
- `filter-features-detailed-config.png` - Detailed view of feature filtering
- `filter-features-advanced-config.png` - Advanced feature filtering settings

### Data Processing
- `select-key-fields-config.png` - Key field selection configuration

### AI Analysis Nodes
- `ai-analysis-config.png` - Main AI analysis configuration
- `sentiment-analysis-config.png` - Sentiment analysis configuration
- `post-summarization-config.png` - Post summarization configuration
- `ai-agent1-title-translation-config.png` - Title translation AI agent configuration

### Data Transformation
- `edit-fields-config.png` - Field editing and transformation configuration

### Data Merging
- `merge-input-config.png` - Input merging configuration
- `merge-3-inputs-config.png` - Three-way data merging configuration

### Data Storage
- `google-sheets-config.png` - Google Sheets output configuration
- `sheets-query-config.png` - Google Sheets query configuration for deduplication

## Screenshot Usage

These screenshots are referenced in the main README.md file to provide visual documentation of each node's configuration. They help users understand:

1. **Node Settings**: Exact parameter values and configuration options
2. **Data Flow**: How data moves between nodes
3. **AI Prompts**: Specific prompts used for AI analysis
4. **Field Mappings**: How data fields are transformed and mapped
5. **Integration Setup**: API connections and authentication requirements

## File Naming Convention

Screenshots follow the pattern: `[node-name]-config.png`
- Use lowercase with hyphens for node names
- Add `-config` suffix to indicate configuration screenshot
- Use descriptive names that match the node's function

## Maintenance

When updating the workflow:
1. Take new screenshots of modified nodes
2. Update the corresponding image files
3. Ensure README.md references are updated
4. Maintain consistent image quality and cropping
