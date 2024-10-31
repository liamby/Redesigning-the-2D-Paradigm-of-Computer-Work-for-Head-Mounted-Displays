# TL; DR
This repository contains research I conducted on the topic of redesigning computer work applications for head mounted displays (HMDs). This research was conducted as part of my Master's degree in Computer Science, specializing in Augmented and Virtual Reality, from Trinity College Dublin. The full academic paper is available [here](https://github.com/liamby/Redesigning-the-2D-Paradigm-of-Computer-Work-for-Head-Mounted-Displays/blob/main/Redesigning%20the%202D%20Paradigm%20of%20Computer%20Work%20for%20Head%20Mounted%20Displays.pdf). This research comprises **two primary segments**, the **research phase** and the **implementation phase**. 

### Research Phase - Researching The Use of HMDs For Computer Work and Establishing Redesign Guidelines
This part begins by clarifying VR terminology to dispel common misconceptions and progresses to provide a technical overview of current VR headsets, laying a foundation for subsequent design considerations. The research narrows its focus on the application of VR for computer-related tasks, analysing existing studies and emphasising design suggestions that limit content placement areas. Recognizing that limitless spatial content can hinder user-friendly design, especially for extended use, the study emphasises the need for specific content zones, driven by technical and ergonomic considerations. Within these defined zones, the research explores content types best suited for adaptation from 2D settings and identifies components that can be optimised for the spatial features of HMDs.

A tri-component framework is introduced for the redesign process, encompassing 1) windows to incorporate and adapt existing 2D content, benefitting from depth-based information hierarchy, 2) volumetric visualisations or 3D objects to augment the user experience, and 3) virtual environments that guide user interactions in line with the designer's intent. The research phase culminates with 20 pivotal guidelines for transitioning computer work to HMDs, aiding designers in proficiently utilising the three components to reimagine their work applications for an immersive environment.

### Implementation Phase - Designing and Implementing a Work Application for HMDs
The second part of the report demonstrates the redesigned of a 2D computer work application into useful 3D experiences by focussing on breaking the existing application into smaller components and rethinking their spatial organisation in a 3D environment based on the conducted research. The aim was to implement and test the suggested approach to redesigning components discovered during the research phase such as the 3-part component framework and 20 user centric design guidelines. The application served as a testing ground to assess the practicality and efficacy of the guidelines, guaranteeing that they not only appear promising in theory but truly enhance an intuitive, immersive, and comfortable VR experience. 

The redesigned application focussed on the common task of conducting research and taking notes and approached the problem from a novel visualisation standpoint. The application was built in Unity and has a client server model allowing the computationally intensive tasks to be offloaded from the headset to a more powerful computer. The application features selective passthrough with hand and keyboard tracking for intuitive user input for the panoramic windows, volumetric interface and immersive environment. There is a video demonstration available for the developed application here.

<br>
&nbsp;

![DissertationImg](https://github.com/liamby/Redesigning-the-2D-Paradigm-of-Computer-Work-for-Head-Mounted-Displays/assets/60388361/346ec4ba-90ac-46e9-a6b9-261b2878316c)

 > Figure. A mockup of a computer work application with windows, a volume and a virtual environment.

 # Abstract

The rise of HMDs brings forth possibilities for reimagining computer work in more immersive and productive ways indicating a shift in how humans interact with computers. HMDs and spatial interfaces are progressing towards becoming an alternative to two dimensional computer interactions. Designing mixed reality (MR) interfaces, which are more complex compared to desktop interfaces, requires standards for creating applications especially when leveraging the spatial capabilities of HMDs. Before HMDs can be widely adopted for tasks the tools currently used in a two-dimensional context will need to be redesigned to take advantage of the third dimension depth. This paper offers design guidelines for developing computer work applications for HMDs. These guidelines along with a methodology for redesigning 2D computer work for virtual environments are demonstrated through a sample application that explores how MR can enhance the research process. Findings from the design and implementation of this project, such as areas to focus the redesign around, are then shared to benefit future projects in the rapidly evolving field of interface design for HMDs.

# Introduction

New possibilities for human-computer interaction have been created by the introduction of HMDs,
including augmented and virtual reality devices. While current usage of MR has been primarily
content consumption, there is untapped potential for more productive and creative use. There is now a
growing need to explore and expand the possibilities offered by HMDs spurred by technology
advances and investment interest in MR. A promising area, which has the potential to revolutionise
how we work with computers, is redesigning the 2D paradigm of computer work for the use of
HMDs. More immersive and efficient work environments could thus be created that will ultimately
enhance productivity and user experience.

Digital interfaces that allow people to use their bodies and the space in which they exist to complete
tasks have belonged thus far to the realm of science fiction, but efforts are now being made to bring
this technology to life, providing users with a more immersive and instinctive way of interacting with
computer systems. HMDs and spatial interfaces could soon be widely used in the workplace as a valid
alternative or addition to conventional two-dimensional computer-based work.

The limited adoption of MR applications can be attributed, in part, to the difficulties involved in
developing applications. Specifically the design of interfaces for MR applications is more intricate
and demanding compared to interfaces, for desktop based applications.

In an environment where HMDs become the primary way to interact with your computer or the
computer itself, new standards will need to emerge for creating applications. How would a designer
go about designing or more likely redesigning their application for this new medium? While
conventional interfaces mainly use 2D graphical displays, MR interfaces use both 2D and 3D
displays. How can they effectively utilise the spatial capabilities of HMDs to create more intuitive
and immersive user experiences than with traditional 2D displays?

Given that HMD technology is constantly improving and is gaining increased attention from investors
and developers, as a new computing paradigm, it seems logical that increasing thought should be put
into how to design for these new interfaces. It seems particularly important to consider interface
design in a working environment as the average knowledge worker spends a significant amount of
time in front of a computer screen and relies heavily on the interface to perform their tasks efficiently
and effectively. This project will focus on how interfaces should be designed for HMDs to best take
advantage of the added z dimension (depth) which they enable.

Contemplating this, the following query was posed: Is it possible to reimagine the conventional
two-dimensional model of computer work for use with HMDs? This inquiry presents an intriguing
aspect—design. The concept of design suggests a systematic approach to redesigning computer work
for MR, considering various factors that influence the process.

Before this shift in the computing paradigm can occur, fundamental questions need to be addressed
and challenges overcome. Only then could we transition smoothly to the implementation of HMDs in
creative and productive applications. Naturally, the tools that are designed for traditional 2D screens,
are not tailored to the unique demands and capabilities of HMDs. As an example, until recently, users
couldn't see their physical keyboard while working in an immersive VR environment, making text
Design for MR Work Applications entry and data input very difficult. Integrating and allowing for the interaction of two-dimensional
content in a three-dimensional environment presents further challenges.

This relatively new field of interface design for HMDs necessitates the discovery of design principles
and their implementation. This rapidly evolving field requires a well-rounded research approach in
order to remain current. This paper outlines design guidelines for HMDs work applications and
presents a demo application that showcases these guidelines in action, accompanied by anecdotal
findings regarding the design and implementation of the system, which will hopefully help inform
future work in this field.

The design guidelines and methodology in this report focus on adapting 2D screens for spatial
computing by a) projecting them into 3D space within a custom virtual environment and b)
augmenting the experience with a volumetric interface. The primary benefit of adopting this
methodology is its ability to adapt existing 2D tools for use with HMDs while leveraging the unique
benefits of 3D visualisation and interaction. This means that rather than starting from scratch,
developers and designers can build upon existing 2D tools and workflows, enhancing them with
spatial computing capabilities. This approach allows for a more seamless transition for users
accustomed to traditional 2D interfaces and reduces the learning curve associated with adopting a
completely new operating system.

In the first half of the report how to redesign work applications for HMDs based on research is
discussed. In the second half, these research findings are applied and in evaluating the resulting
application, foundational knowledge for future endeavours aimed at creating VR tools tailored for
computer work is gained.

### See video demonstration at https://www.youtube.com/watch?v=Bb-M3jQZ8BE
