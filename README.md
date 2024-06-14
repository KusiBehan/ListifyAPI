## Die ListifyAPI bietet eine Reihe von Endpunkten für die Verwaltung von Tasks. Funktionen zum Erstellen, Abrufen, Aktualisieren und Löschen von Aufgaben werden von dieser REST API berücksichtigt.
## Endpoints Beschreibung
####  Get All Tasks

- **Endpoint**: `/tasks`
- **Method**: `GET`
- **Description**: Retrieves a list of all tasks.
- **Response**: `TObjectList<TTask>`: 
```
[
  {
    "id": 1,
    "title": "Task 1",
    "description": "Description of Task 1",
	...
  },
    {
    "id": 2,
    "title": "Task 2",
    "description": "Description of Task 2",
    ...
  },
  ...
]
```

#### Get Task by ID

- **Endpoint**: `/task/{ID}`
- **Method**: `GET`
- **Description**: Retrieves a task by its ID.
- **Path Parameter**:
    - `ID` (integer): The ID of the task to retrieve.
- **Response**: `TTask`

```
{   
	"id": 1,
	"title": "Task 1",
	"description": "Description of Task 1"
	...
}
```

#### Create Task

- **Endpoint**: `/tasks`
- **Method**: `POST`
- **Description**: Creates a new task.
- **Request Body**: `TTask`
```
{ 
	"title": "New Task",
	"description": "Description of the new task",
	"creationDate "^: 
}
```

  - Response: `IMVCResponse`
```
  {
  "status": "success",
  "message": "Task created successfully",
  "data": {
    "id": 1,
    "title": Titel 
  }
}
```
#### Update Task

- **Endpoint**: `/task/{ID}`
- **Method**: `PUT`
- **Description**: Updates an existing task by its ID.
- **Path Parameter**:
    - `ID` (integer): The ID of the task to update. 
- **Request Body**: `TTask`
```
{
	"id": 1,
	"title": "Updated Task",
	"description": "Updated description of Task"
}	
```
- **Response**: `IMVCResponse`
```
  {
  "status": "success",
  "message": "Task created successfully",
  "data": {
    "id": 1,
    "title": Titel 
  }
}
```

#### Delete Task

- **Endpoint**: `/task/{ID}`
- **Method**: `DELETE`
- **Description**: Deletes a task by its ID.
- **Path Parameter**:
    - `ID` (integer): The ID of the task to delete.
- **Response**: `IMVCResponse`
```
	{
	 "status": "success",
	  "message": "Task deleted successfully"
	}
```
## Task Entity Beschreibung

#### Übersicht

Die Entität `TTask` repräsentiert eine Aufgabe mit verschiedenen Attributen wie ID, Titel, Beschreibung, Status und Erstellungsdatum. Diese Entität wird im Kontext der Aufgabenverwaltungs-API verwendet, um die Details einer Aufgabe zu kapseln.

#### Eigenschaften

1. **ID**
    
    - **Typ**: `Integer`
    - **Beschreibung**: Eine eindeutige Kennung für die Aufgabe.
    - **Getter/Setter**: `read FID write FID`
2. **Titel**
    
    - **Typ**: `String`
    - **Beschreibung**: Der Titel der Aufgabe.
    - **Getter/Setter**: `read FTitle write FTitle`
3. **Beschreibung**
    
    - **Typ**: `String`
    - **Beschreibung**: Eine detaillierte Beschreibung der Aufgabe.
    - **Getter/Setter**: `read FDescription write FDescription`
4. **Status**
    
    - **Typ**: `boolean`
    - **Beschreibung**: Der Status der Aufgabe (true für abgeschlossen, false für offen).
    - **Getter/Setter**: `read FStatus write FStatus`
5. **Erstellungsdatum**
    
    - **Typ**: `TDate`
    - **Beschreibung**: Das Datum, an dem die Aufgabe erstellt wurde.
    - **Getter/Setter**: `read FDateOfCreation write FDateOfCreation`
#### Json Darstellung

```
{
"id": 1,
"title": "Beispielaufgabe",
"description": "Dies ist eine Beispielaufgabenbeschreibung.",
"status": true,
"dateOfCreation": "2024-06-14"
}
```
