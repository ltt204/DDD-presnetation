# Domain-Driven Design Presentation

A comprehensive presentation on Domain-Driven Design (DDD) concepts and practices, created for HCMUS Software Engineering course.

## 📚 Overview

This presentation covers the fundamental concepts of Domain-Driven Design, a modeling technique that allows for organized decomposition of complex problem domains. The content explores how DDD helps bridge the gap between business requirements and software implementation.

## 👥 Authors

- **Lý Trọng Tín**
- **Phan Thanh Tiến**

**Institution:** Ho Chi Minh City University of Science (HCMUS)  
**Course:** Software Engineering  
**Date:** May 2025

## 📖 Table of Contents

1. **First Look**
   - What is Domain-Driven Design?
   - Why do we need DDD?
   - Who needs to understand the Domain?

2. **Core Concepts of DDD**
   - Domain
   - Model & Domain Model
   - Ubiquitous Language

3. **Model-driven Design**
   - Traditional Development Process Issues
   - Structured Domain Model:
     - Entity
     - Value Object
     - Domain Service
     - Aggregate

4. **Subdomain**
   - Core Subdomain
   - Generic Subdomain
   - Supporting Subdomain

5. **Event Storming**
   - Domain Events
   - Commands
   - Aggregates
   - Policies
   - Bounded Context

## 🎯 Key Learning Objectives

- Understand the complexity challenges in software development
- Learn how to model complex business domains effectively
- Master the core building blocks of DDD
- Apply Event Storming techniques for domain exploration
- Recognize different types of subdomains and their strategic importance

## 🛠 Technologies Used

- **Marp** - For creating the slide presentation from Markdown
- **Draw.io** - For creating diagrams and visual representations
- Custom CSS styling for enhanced presentation design

## 📁 Project Structure

```
presentation-ddd/
├── Domain-driven design.md     # Main presentation content
├── Domain-driven design.pdf    # PDF export of presentation
├── README.md                   # This file
└── assets/                     # Images and diagrams
    ├── aggregate.drawio.png
    ├── domain-service.drawio.png
    ├── entity-vo-anwser.drawio.png
    ├── entity-vo-ques.drawio.png
    ├── event-storming.png
    ├── HCMUS-logo.png
    ├── Hong-Sang-Linkedin.png
    ├── netflix-architecture.png
    └── water-fall.png
```

## 🚀 Getting Started

### Prerequisites

- [Marp CLI](https://github.com/marp-team/marp-cli) for generating presentations
- Markdown editor (VS Code recommended)

### Viewing the Presentation

1. **Markdown Format**: Open `Domain-driven design.md` in any Markdown editor
2. **PDF Format**: View `Domain-driven design.pdf` directly
3. **Live Presentation**: Use Marp to serve the presentation:
   ```bash
   marp --serve Domain-driven\ design.md
   ```

### Exporting to Different Formats

```bash
# Export to HTML
marp Domain-driven\ design.md --html

# Export to PDF
marp Domain-driven\ design.md --pdf

# Export to PowerPoint
marp Domain-driven\ design.md --pptx
```

## 🔑 Key Concepts Covered

### Core DDD Building Blocks

- **Entity**: Objects with unique identity that persist through lifecycle changes
- **Value Object**: Immutable objects defined by their attributes rather than identity
- **Domain Service**: Stateless services that contain business logic not belonging to any specific entity
- **Aggregate**: Clusters of related objects treated as a single unit for data changes

### Strategic Design Patterns

- **Subdomain Classification**: Core, Generic, and Supporting subdomains
- **Bounded Context**: Clear boundaries for model applicability
- **Context Mapping**: Understanding relationships between different contexts

### Tactical Patterns

- **Event Storming**: Workshop technique for domain exploration
- **Ubiquitous Language**: Shared vocabulary between domain experts and developers

## 📚 References

### Books
- [Domain-Driven Design: Tackling Complexity in the Heart of Software](https://www.google.com.vn/books/edition/Domain_Driven_Design/hHBf4YxMnWMC?hl=en&gbpv=0) - Eric Evans
- [Domain-Driven Design Quickly](https://www.google.com.vn/books/edition/Domain_Driven_Design_Quickly/CfdHAgAAQBAJ?hl=en&gbpv=1&printsec=frontcover)
- [Implementing Domain-Driven Design](https://www.google.com.vn/books/edition/Implementing_Domain_Driven_Design/X7DpD5g3VP8C?hl=en&gbpv=1&dq=Implementing+Domain&printsec=frontcover) - Vaughn Vernon

### Additional Resources
- [Domain-Driven Design Blog](https://organic-potential-e5b.notion.site) - Our detailed blog posts on DDD concepts and practices

## 🙏 Acknowledgments

Special thanks to:
- **NGUYEN Hong San** for guidance and discussions
- [Github Discussion - Tập viết](https://github.com/hongsan/random/discussions)
- [LinkedIn - NGUYEN Hong San](https://www.linkedin.com/in/nguyenhongsan/)

## 📄 License

This presentation is created for educational purposes as part of the HCMUS Software Engineering curriculum.

---

**Note**: This presentation uses the Marp framework with custom styling and incorporates various diagrams and real-world examples to illustrate DDD concepts effectively.