# Requirement

## What Is character?

<procedure>
<list>
<li>
A unified platform that allows you to seamlessly collaborate with your team—all without ever leaving your tab.
</li>
<li>
A comprehensive toolkit that brings together everything you need for work, including chat, task management, file storage, and more.</li>
</list>
</procedure>

## Use case

```plantuml
@startuml
left to right direction

actor User as "User"
actor OrgMember as "Organization Member"
actor GroupChatMember as "Group Chat Member"

package Auth0 {
    usecase SU as "Sign Up"
    usecase SI as "Sign In"
}

package Organization {
    usecase CNO as "Create a new organization"
    usecase SBO as "Switch between organizations"
    usecase INM as "Invite new member to the organizations"
    
    package GroupChat {
        usecase CNG as "Create a new group chat"
        usecase AMGC as "Add new members to a group chat"
        usecase SMGC as "Send messages to a group chat"
    }
}

User ---> SU
User ---> SI
User ---> CNO

OrgMember --> SBO
OrgMember --> INM
OrgMember --> CNG

GroupChatMember --> AMGC
GroupChatMember --> SMGC

@enduml
```

## Navigation Diagram

```plantuml
@startuml

[Landing page] as landing
[Sign In page] as signIn
[Sign Up page] as signup
[Workspace] as workspace

landing --- signIn
landing --- signup
landing --- workspace

signIn --- workspace
signup --- workspace

@enduml
```

## UI/UX
[//]: # (TODO)

## Entity Relationship

```plantuml
@startuml

package Auth0 {
    entity User {
    }
}

package Organization {
    entity Organization {
    }
    
    package GroupChat {
        entity GroupChat {
        }
    }
}

@enduml
```