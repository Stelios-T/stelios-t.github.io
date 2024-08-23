---
title: "Intelligent application of the principle of data minimization"
date: 2022-09-22T10:30:02-05:00
categories:
  - blog
tags:
  - data
  - java
  - gdpr
  - rdf
  - privacy
---

**Note**: This is not the complete representation of the project. For the full project details, please visit the GitHub repository linked at the end of this page.


The issue of privacy and data protection is becoming increasingly important and legislated, making it one of the critical concerns for modern societies. The vast amount of data collected and processed, especially with the advancement of technology, is the main reason behind this concern. To address these issues, the European Union introduced the General Data Protection Regulation (GDPR). One of the core principles of the GDPR is data minimization, which ensures that only data that is adequate, relevant, and necessary for a specific purpose is collected and processed.

This repository aims to present a technical solution for applying the data minimization principle. It introduces an innovative system that leverages semantic web technologies to make real-time decisions about which data meets the minimization criteria.

## RDF MODEL 

An RDF (Resource Description Framework) model was created to represent a knowledge graph that illustrates the relationships between types of personal data and the services that use them. Specifically, two interconnected graphs were developed: the PersonalDataGraph and the ServicesGraph. These graphs use namespace identifiers to distinguish between data types and services. For clarity, the prefix data: is used for types of personal data, while service: is used for types of services.

#### PersonalDataGraph:

![Screenshot 2022-09-21 143735](https://user-images.githubusercontent.com/67365815/203770295-b675b1de-0bbe-4056-bf0b-a3dfd6dc45a4.jpg)


#### ServicesGraph:

![Screenshot 2022-09-21 152843](https://user-images.githubusercontent.com/67365815/203770345-dabfc826-7e60-4978-894e-fa1379012491.jpg)


#### Final Model:
![Screenshot 2022-09-09 145404](https://user-images.githubusercontent.com/67365815/203770370-d809e080-2e75-418d-b08d-b2a37fde2509.jpg)



## Personal Data and Services

The types of personal data and services used in this project can be seen in the Final Model above.

## How to run

The system is built as a MAVEN project. To get started, download the code and run it as is.


## Testing


In ```MainModel.java``` 


**Add the type of personal data to test** 

```
service_required_data.add("data: <Personal Data> ");
```

*Example:*
```
service_required_data.add("data:IDCard");
service_required_data.add("data:Email");
service_required_data.add("data:IsAdult");
```


**Add the type of service to test with the personal data** 

```
filter.DataMinimizationFilter("service: <Service> ", service_required_data);
```

*Example:*
```
filter.DataMinimizationFilter("service:SubscriptionSignUp", service_required_data);
```


For more details, visit the ![GitHub repository](https://github.com/Stelios-T/Data-Minimization-System).