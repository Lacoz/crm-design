# 

```mermaid
C4Context
title CRM CZ (Pre-Unification Era)

Person(sales, "Sales team", "Uses Central CRM")
Person(inno, "InnoOne team", "Develops Inno Solution Layer and Integration Platform")
Person(iss, "ISS (CZ) team", "Operates and manages Central CRM")
Person(teamioTeam, "Teamio team", "Uses Teamio and InnoOne Integration Platform")

System(crm, "Central CRM", "Core CRM platform")

System_Boundary(innoBoundary, "InnoOne – Solution & Integration") {
    System(innoSolution, "Inno Solution Layer", "Solution subsystem developed by InnoOne for Central CRM")
    System(innoInt, "InnoOne Integration Platform", "Connects Teamio and product systems to Central CRM")
}

System(teamio, "Teamio", "Recruitment / HR platform")

System_Boundary(prodBoundary, "Product Teams") {
    System(prod1, "Product Team 1 System", "Integrated via Teamio")
    System(prod2, "Product Team 2 System", "Integrated via Teamio")
}

Rel(sales, crm, "Uses")
Rel(inno, innoSolution, "Develops")
Rel(inno, innoInt, "Develops and maintains")
Rel(iss, crm, "Operates and manages")
Rel(teamioTeam, teamio, "Uses")
Rel(teamioTeam, innoInt, "Uses integration services")

Rel(innoSolution, crm, "Extends")
Rel(innoInt, crm, "Integrates with")

Rel(prod1, teamio, "Integrates with")
Rel(prod2, teamio, "Integrates with")
Rel(teamio, innoInt, "Uses")

```
