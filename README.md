# Art Gallery
This Application developed using Oracle APEX's low-code platform using features like Drag-and-drop tools, pre-built templates, and visual modeling for rapid development. 
<!-- Your hidden command or note here -->

## Application Description
The Art Gallery application is a low-code platform-based project designed for efficiently managing and displaying artworks. It enables users to explore various artworks in galleries, view information about individual artworks, manage profiles, and interact with features like title, hearts and downloads. This application is built for both administrators and general users for interacting and managing resources.


## Set up and Installation
- Prerequisites: Oracle Database (based on requirements), JavaScript-enabled browser and At least 300 MB of memory.
- Create Oracle Workspace using either Local IP Address or Web Application.
- Request new workspace when accessing through website.
- Enter all essential credentials and complete identification and verification process.
- Remember or auto save Workspace name, User name and Password information for future access.
- Note: Workspace will be purged upon prolonged months of inactivity with email notice.

  
## Repository Structure
<!-- development_captures
│   ├── AppBuilder.png
│   ├── Art_Info.png
│   ├── Artwork.png
│   ├── Artwork_Search.png
│   ├── Breadcrumb_Entries.png
│   ├── Dashboard.png
│   ├── Navigation.png
-->
<!-- application_captures
│   ├──Art_Info_Insertion.png
│   ├──Art_Info_Overview.png
│   ├──Artwork_Filter_Overview.png
│   ├──Artwork_Search_KeywordSearch.png
│   ├──Artwork_Search_OrderBy_Hearts.png
│   ├──Artwork_Search_OrderBy_Title.png
│   ├──Dashborad_Overview1.png
│   ├──Dashborad_Overview2.png
│   ├──Homepage_Overview.png
│   ├──User_Profile_Overview.png
-->
```
LowCode-Application/
│
├── src/
│   ├── sql_queries                  # Contains all sql queries for creating table, procedure and trigger
│
├── assets/
│   ├── development_captures/        # Conatins screenshot of raw Low code development pages
│   ├── application_captures/        # Contains screenshot of Live application to end users
│
├── README.md                        # Summary
```

  
## Application Development Structure
The Art Gallery low-code application is structured as following pages for backend development:
- Gallery
- Art_Info
- Artwork
- User_Profile
- Profile
- Artwork_Search
- Dashboard


## Application Pages
The Art Gallery application has following tags for frontend interaction:
- Gallery
- Info
- Profile
- Search
- Filters
- DashBoard


## Page Descriptions
### Gallery
   - Displays all available artworks in a list format present in Database.
   - Artworks are identified using features like AW id, AW Title, Aw Hearts and Aw Downloads.
   - Users can browse through thumbnails with titles.

### Info
   - Provides detailed information about a selected artwork.
   - Includes AW Title, Aw Hearts and Aw Downloads.
   - Allows user to select and identify each artwork available

### Profile
   - Displays the logged-in user's profile details.
   - Feature includes user and bio information.
   - Also allows viewvers to create new login credential.

### Search
   - Search functionality for finding specific artworks based on keywords or filters.
   - Results are displayed dynamically.

### Filters
   - Displays artworks in list based on desired filter that is applied.
     
### Dashboard
  - Displays visual representation for analyzing various metrics.
  - Chart1 displays hearts obtained by each painting as line graph.
  - Chart2 displays pie chart based on downloads for each painting.
  - Chart3 displays bar graph for hearts attained by each painting.


## Key Low Code Features 
### Navigation and User Interface
- Navigation list implemented for accessing various pages in application.
- Breadcrumb navigation to help users understand their location within the application
- Interactive grids for displaying and managing artwork data, allowing sorting, filtering, and inline editing

### Data Management and CRUD Operations
- CRUD (Create, Read, Update, Delete) operations for entities like users, artworks, hearts and downloads.
- Implementation of stored procedures and triggers for other complex operations.
- Data validation imposed using various SQL constraints.

### Security and Authentication
- Role-based access control utilizing the 'rol' column in the user table.
- Login page with session management for user authentication.
- Implementation of database triggers for data integrity and security (e.g., Update_Art_Title trigger)

### Reporting and Analytics
- Interactive reports for displaying complex queries, such as popular artworks or user engagement metrics
- Charts and dashboards for visualizing data like download counts and hearts related to artwork popularity.

### Dynamic Content and Conditional Rendering
- Conditional rendering of regions, items, or buttons based on user roles or data values.
- Customized titles and labels for regions, charts, and form fields using substitution strings
- Cascading select lists for related data (e.g., selecting artworks based on categories)

### Search and Filter Functionality
- Advanced search capabilities for artworks, likely implemented using dynamic SQL queries
- Filter options based on various artwork attributes (e.g., title, hearts, downloads)


## Advantages of Low-Code in Application Development
- Faster Development: Reduces application development time by up to 90% through drag-and-drop functionality and pre-built templates.
- Cost Efficiency: Reduced need for specialized developers lowers costs while maintaining high-quality output.
- Improved Collaboration: Understandable interfaces allow business users to participate in development alongside IT teams.
- Agility: Applications can be quickly adapted to changing requirements without extensive redevelopment.
- Ease of Maintenance: Pre-tested components ensure minimal debugging and maintenance efforts.

## Conclusion
With focus on simplicity, scalability and rapid development this project exemplifies how low-code platforms can transform the overall application development process. 

