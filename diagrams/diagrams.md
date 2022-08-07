# Diagrams

## Flowchart

```mermaid
flowchart TD
    node1[Does my question require ranking recursion, moving calculations, or inter-row calculations to answer it? ] --> |No| node3[Use a Table Calculation]
    node1 --> |Yes| node2[Do I already have all the data values I need on the visualization?]
    node2 --> |Yes|node3
    node2 --> |No| node4[Does the granularity of the question match either the granularity of the visualization or the data source?]
    node4 -->|No| node5[Use LOD expression]
    node4 --> |Yes| node6[Use basic expression]

```

Reference: [CalcsBasics_flowchart4.png (1081×580)](https://help.tableau.com/current/pro/desktop/en-us/Img/CalcsBasics_flowchart4.png)

## Sequence Diagram

```mermaid
sequenceDiagram
    actor Alice
    participant View
    participant Controller
    participant Model
    Alice->>View:1.Fire Update Event
    View->>Controller:2.requestUpdate()
    Controller->>Model:3.updateState()
    View->>Model:4.requestData()
    Model-->>View:5.return state
```

## Gantt Diagram

```mermaid
gantt
dateFormat  DD-MM-YYYY
title Gantt Diagram
excludes    weekends

section A section
Planning            :done,      des1, 18-07-2022,1w
Research            :done,      des2, 25-07-2022,3d
Design              :active,    des3, after des2,3d
Implementation      :           des4, after des3,1w
Bugfixes            :           des5, after des4,3d
```

## Class Diagram

```mermaid
classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
      +String beakColor
      +swim()
      +quack()
    }
    class Fish{
      -int sizeInFeet
      -canEat()
    }
    class Zebra{
      +bool is_wild
      +run()
    }

```

## State Diagramm

```mermaid
stateDiagram-v2
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

## Pie Chart

```mermaid
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

## Git Graph

```mermaid
    gitGraph
      commit
      commit
      branch develop
      checkout develop
      commit
      branch feature-branch
      checkout feature-branch
      commit
      commit
      commit
      checkout develop
      merge feature-branch
      commit
      checkout main
      merge develop
      commit
      commit
```

## ER Diagram

```mermaid
erDiagram
          CUSTOMER }|..|{ DELIVERY-ADDRESS : has
          CUSTOMER ||--o{ ORDER : places
          CUSTOMER ||--o{ INVOICE : "liable for"
          DELIVERY-ADDRESS ||--o{ ORDER : receives
          INVOICE ||--|{ ORDER : covers
          ORDER ||--|{ ORDER-ITEM : includes
          PRODUCT-CATEGORY ||--|{ PRODUCT : contains
          PRODUCT ||--o{ ORDER-ITEM : "ordered in"
```

## User Journey Diagram

```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```
