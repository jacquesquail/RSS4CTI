# RSS4CTI
- Flask App
- Python RSS Fetcher
- SQLite Database
- NLP extractors / Maybe LLM?
- Fever API

## Web Interface
- Threat Dashboard
- Threat Explorer
- Feed List
- Notifications
- Settings

### Settings
- API Settings
- Notification
- LLM (ChatGPT) / NLP settings
- Feed conditional categorisation
- Entity conditional categorisation

## Database Schema
### Feeds
List of RSS feeds and their feed URL's
- Feed ID - PKey
- Feed GUID
- Feed Name
- Feed Description
- Feed URL
- Refresh Interval

### Entries
List of feed entries
Entry Categories (Vulnerability, Ransomware, Espionage, Zero Day, Data Breach, Termination, Emergence)
- Entry ID
- Entry GUID - PKey
- Feed ID - FKey
- Entry Title
- Entry Author
- Entry Content
- Entry Link
- Entry Date
- Entry isRead
- Entry isFavourited
- Entry Categories


### Entities
List of CTI entities and their related article 
Entity Categories (Organisation, Sector, Actor, Country, Malware, CVE, Vendor, IP Address, Hash, Domain)
Entity Origin = RSS4CTI will attempt to associate an Entity with a parent entity that's the most relevant for the article (e.g. Country > Actor, Actor > Malware). The number of duplicate relationships could increase confidence.
- Entity ID
- Entity GUID - PKey
- Entity Title
- Entity Category
- Entity Origin
- Entity Entry ID - FKey