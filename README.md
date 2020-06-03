## Microsoft PowerApps

## Visit a business App

Watch the video to "see what you get" [`Visit a Business.mp4`](https://github.com/VisitABusiness/VisitABusiness/blob/master/Visit%20a%20Business%20V3.mp4)

To start the deployment, download the [`Solution deployment.docx`](https://github.com/VisitABusiness/VisitABusiness/blob/master/Solution%20Deployment.docx) and follow the instructions.

## **Visit a Business solution package**

The solution is provided as a template in the form of:

- A Power Platform solution file containing most of the configuration for the overall implementation
- Instructions to set up further configuration specific to typical customer needs
- Data import examples
- Instructions how to use the apps

## **Objective and design**

The purpose of this document is to give an overview of the &quot;visit a business&quot; application built on Power Platform to assist organisations with managing visits to their physical branches or stores to ensure social distancing.

The solution is designed to manage to approximate capacity, optimised for scalability rather than guaranteeing a specific capacity. While in general bookings will be held within the specified capacity, if multiple bookings are made at the exact same time then the solution approach does not attempt to serialise to ensure over booking.

In reality, the expected scenario is for managing capacity for estimate appointment lengths only and therefore capacity is defined as an assessment of throughput possible during that slot, and also that as there is no payment or specific commitment made to appear, that there would likely also be people not attending to booked appointments, therefore the scalability implications of serialisation to guarantee managing to a specific capacity is not required.

For larger organisations, volumes could grow both for slot management and bookings, but as there is no purpose to maintaining historical records, the expectation is that a deletion job would be set up to delete historical records the day after they occur keeping volumes low and optimising the deletion approach.

Privacy has been considered strongly as part of this and can be adjusted by the end customer to their needs. The template solution captures the minimal personal information:

- There is no direct need for any personal information within this solution, but this minimum has been captured to facilitate checking of attendees at arrival at the branch
- It captures email address to allow for future notification via email of the slot booked but also potentially in the future to search for excessive previous bookings by the same email address and even activated/confirmation of email address if abuse is discovered. Neither of these are implemented today but potential is there for the future.

## **Visit a Business App Purpose**

The purpose of our social distancing branch application is summarised as follows:

- Under social distancing lockdown as countries and organisations open their stores/branches, there is still a need to maintain social distancing ​
- A peak of visits would affect the ability to safely maintain social distancing​
- Provide a way for customers to obtain from an organisation through a call centre/website/mobile app, a pre-arranged time to visit the store, limiting capacity​
- The control being applied here is to limit the number of people travelling to a branch for a specific period
- Once at the branch, the local branch staff will manage a FIFO queue of people to actually enter the store, but that is not the responsibility of the app

## **Visit a Business applications**

The application is implemented as a series of apps on the Microsoft Power Platform, there are different applications for different use cases:

### Branch Admin app

- Allow administration of the system
- Allow branch managers to set up their time slots for their branch

### Booking app

- Allow employee(s) of a business to book an appointment/timeslot on behalf of their customer

### Branch app

- Allow customers to book an appointment/timeslot online at a business

### Power Portal

- Allow customers to book an appointment/timeslot online at a business
