## 1. Application Goal 
To send and receive tickets related to cloud issues.
## 2. Functional Scope 
- Creat an issue
- View all issues
- Change an issue status
## 3. Request Flow 
> ### Create issue: 
> User → Frontend form → POST /api/issues → API validation → Data layer 
>
>← Render created issue ← 201 + JSON ←───────────────┘


> ### View issue:
> Page load → GET /api/issues → API → Data layer 
> 
> ← Render list ← 200 + JSON array ←───┘ 

> ### CHANGE STATUS 
> Button → PATCH /api/issues/{id}/status → API validation → Data layer 
> 
> ← Re-render issue ← 200 + updated JSON ←──────────┘  

## 4. Trust Boundaries 

### USER-CONTROLLED SIDE &emsp;&emsp;&emsp;&emsp;&emsp; APPLICATION-CONTROLLED SIDE 
  
> Browser input  ───── HTTP request ─────▶  REST API  ─────▶  Data 
>
>        ▲                                                   
>        └─────────────── JSON response ◀──────────────────┘