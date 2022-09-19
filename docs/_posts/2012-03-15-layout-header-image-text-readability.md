---
title: "Grader Project"
header:
  image: /assets/images/Grader_article_home.jpg
  # caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
tags: 
  - sample post
  - readability
  - test
---

Working at MEDATech Engineering Services I was able to build upon my undergraduate experience in Software and Electrical design and development. I spent most of my time here around nine months developing a drive-by-wire diesel-powered grader system.

## Responsibilities

As the main Controls Designer, I definitely felt the weight and responsibility of this opportunity and had to rise to the occasion. So, I left no stone unturned. Like many in my position I wanted to know everything there was to this grader and relied on my experience as well as my superiors advice to guide me through it all.

### Research

The research I conducted for this project was extensive in the following areas:

  * Engine controller
  * Hydrostatic controller
  * SIL (Safety Integrity Level) 2 requirements and implementations on fail-safe controllers
  * Configuration of I/O modules and peripheral ECU (electronic control unit)
  * Client documentation

For both the engine and hydrostatic controllers I read and understood the associated documentation (data sheets and manuals). I would learn specific topics within this manual concerning functional requirements from the client such as throttle limitation, cold starting, engine and exhaust braking to name a few. Once I was familiar with the content, I would be the lead in meetings with the OEM requesting time with their technical support. I would question their technical support to clear doubts I had as well as informing them on discrepancies in their documentation. During these meetings I would also confirm with the technical team what I knew regarding how to enable certain functionalities through their specific proprietary software. There would be regular meetings with the client regarding functionalities they wanted to add on.

Cumulating all these resources I would confidently start to configure each controller to their required specification while adhering to safety requirements outlined in the manuals to uphold SIL 2 standards. Adhering to these requirements meant that I needed to communicate with not just one message but a system of primary and redundant messages. This allowed their systems to perform their own fail-safe protocols (request idle engine RPM, limp mode, disable steering, etc) in the event of loss of communications or discrepancies in the information being transmitted/received. These fail-safes are also triggered by checksums, heartbeat counters pr internal request. On the master controller where I wrote the main program, I had to also carry on the same SIL 2 requirements. To ensure that I follow the correct requirements and implementation I read and understood CODESYS Safety SIL2 – IEC Programming Guidelines. Through this document I adhered to standards such as:

  * EN13849
  * EN62061
  * IEC61508
  * IEC61131-3

Following safety requirements such as:

  * Source code reviews
  * Use of libraries
  * Floating point operations
  * Non-naturally-aligned structures
  * Multitasking and I/Os
  * Multiple mapping of I/Os
  * Use of the operators AND_THEN / OR_ELSE
  * Calculation of safe outputs
  * I/O devices without SAFE data types
  * CANopen Safety Stack: cross-communication

That document helped define rules I needed to follow when coding the main program. Even though the clients defined the functional requirements it was our in-house team of engineers that conducted the PHA (Process Hazard Analysis) meetings, following other ISO standards (ISO 15998,#####) . In these meetings I contributed little and made it a point to learn as much as I could from the way the senior engineers would simplify problems to bring about safe measures to dangerous outcomes.

I also read documentation regarding I/O modules and peripheral ECU’s (electronic control units) to configure them to our purposes for the grader. Communication with the I/O modules were crucial due to having many sensors throughout the grader. This eliminated unnecessary wiring and allowed information to be transmitted through the many CAN networks to be received by the master controller. The documentation for the peripheral ECU’s helped interpreting the values and error codes being sent over the CAN Network. The peripheral ECU’s that I worked with are as follows:

  * Wheel angle sensors
  * Linear position sensors
  * Steering valve
  * Articulation valve
  * CAN switches

Regarding these ECU’s I needed to configure their source address, baud rate and heartbeat counter interval while adhering to safety requirements like rolling counters, checksums, and primary and redundant messaging. Specifically, to the steering valve I did extensive research into implementing Ackerman steering and the mathematical relationships that need to be maintained regarding the left and right wheel angles.

While configuring all these components I constantly had to refer to client documentation from their internal repository, to find everything from required parameters for the steering and articulation valves (distance between articulation pivot point and front wheel axle, length of the vehicle, etc) to vehicle characteristics like (idle RPM, max required turning radius/angle, etc). 

This project reconfirmed my notion that research is crucial to building a safe product. Where I had to rely on my interpersonal skills heavily during this phase of the development. Skills like communication, creativity, adaptability, collaboration, and leadership would be the reasons why I felt like everyone had my back during this whole process.

### Concept design / design analysis

Here I wrote and designed the architecture of the software through control/process flow charts, network diagrams and state flow diagrams. I was advised to make the decision to create the master program using as many function blocks through structure text (ST) as I could. This seemed to be the best way forward so that in the event of an issue arising from not complying with any safety requirements, it would be isolated to a minor function block. Additionally, I would use as many SIL 2 certified safety function blocks as I could, as there were already certified. I was responsible for developing the control system for steering, articulation, moldboard functionality, drive, and safe state responses.

Steering Control System
  * Closed loop control

This is a sample post with a large feature image[^1] up top and tons of text. Odio ad blue bottle vinyl, 90's narwhal commodo bitters pour-over nostrud. Ugh est hashtag in, fingerstache adipisicing laboris esse Pinterest shabby chic Portland. Shoreditch bicycle rights anim, flexitarian laboris put a bird on it vinyl cupidatat narwhal. Hashtag artisan skateboard, flannel Bushwick nesciunt salvia aute fixie do plaid post-ironic dolor McSweeney's. Cliche pour-over chambray nulla four loko skateboard sapiente hashtag.

Vero laborum commodo occupy. Semiotics voluptate mumblecore pug. Cosby sweater ullamco quinoa ennui assumenda, sapiente occupy delectus lo-fi. *Ea fashion axe [Marfa cillum aliquip](#). Retro Bushwick keytar cliche.* Before they sold out sustainable gastropub Marfa readymade, ethical Williamsburg skateboard brunch qui consectetur gentrify semiotics. Mustache cillum irony, fingerstache magna pour-over keffiyeh tousled selfies.

## Cupidatat 90's lo-fi authentic try-hard

In pug Portland incididunt mlkshk put a bird on it vinyl quinoa. **[Terry Richardson](#) shabby chic +1**, scenester Tonx excepteur tempor fugiat voluptate fingerstache aliquip nisi next level. Farm-to-table hashtag Truffaut, Odd Future ex meggings gentrify single-origin coffee try-hard 90's.

  * Sartorial hoodie
  * Labore viral forage
  * Tote bag selvage
  * DIY exercitation et id ugh tumblr church-key

Incididunt umami sriracha, ethical fugiat VHS ex assumenda yr irure direct trade. Marfa Truffaut bicycle rights, kitsch placeat Etsy kogi asymmetrical. Beard locavore flexitarian, kitsch photo booth hoodie plaid ethical readymade leggings yr.

Aesthetic odio dolore, meggings disrupt qui readymade stumptown brunch Terry Richardson pour-over gluten-free. Banksy american apparel in selfies, biodiesel flexitarian organic meh wolf quinoa gentrify banjo kogi. Readymade tofu ex, scenester dolor umami fingerstache occaecat fashion axe Carles jean shorts minim. Keffiyeh fashion axe nisi Godard mlkshk dolore. Lomo you probably haven't heard of them eu non, Odd Future Truffaut pug keytar meggings McSweeney's Pinterest cred. Etsy literally aute esse, eu bicycle rights qui meggings fanny pack. Gentrify leggings pug flannel duis.

## Forage occaecat cardigan qui

Fashion axe hella gastropub lo-fi kogi 90's aliquip +1 veniam delectus tousled. Cred sriracha locavore gastropub kale chips, iPhone mollit sartorial. Anim dolore 8-bit, pork belly dolor photo booth aute flannel small batch. Dolor disrupt ennui, tattooed whatever salvia Banksy sartorial roof party selfies raw denim sint meh pour-over. Ennui eu cardigan sint, gentrify iPhone cornhole.

> Whatever velit occaecat quis deserunt gastropub, leggings elit tousled roof party 3 wolf moon kogi pug blue bottle ea. Fashion axe shabby chic Austin quinoa pickled laborum bitters next level, disrupt deep v accusamus non fingerstache.

Tote bag asymmetrical elit sunt. Occaecat authentic Marfa, hella McSweeney's next level irure veniam master cleanse. Sed hoodie letterpress artisan wolf leggings, 3 wolf moon commodo ullamco. Anim occupy ea labore Terry Richardson. Tofu ex master cleanse in whatever pitchfork banh mi, occupy fugiat fanny pack Austin authentic. Magna fugiat 3 wolf moon, labore McSweeney's sustainable vero consectetur. Gluten-free disrupt enim, aesthetic fugiat jean shorts trust fund keffiyeh magna try-hard.

## Hoodie Duis

Actually salvia consectetur, hoodie duis lomo YOLO sunt sriracha. Aute pop-up brunch farm-to-table odio, salvia irure occaecat. Sriracha small batch literally skateboard. Echo Park nihil hoodie, aliquip forage artisan laboris. Trust fund reprehenderit nulla locavore. Stumptown raw denim kitsch, keffiyeh nulla twee dreamcatcher fanny pack ullamco 90's pop-up est culpa farm-to-table. Selfies 8-bit do pug odio.

### Thundercats Ho!

Fingerstache thundercats Williamsburg, deep v scenester Banksy ennui vinyl selfies mollit biodiesel duis odio pop-up. Banksy 3 wolf moon try-hard, sapiente enim stumptown deep v ad letterpress. Squid beard brunch, exercitation raw denim yr sint direct trade. Raw denim narwhal id, flannel DIY McSweeney's seitan. Letterpress artisan bespoke accusamus, meggings laboris consequat Truffaut qui in seitan. Sustainable cornhole Schlitz, twee Cosby sweater banh mi deep v forage letterpress flannel whatever keffiyeh. Sartorial cred irure, semiotics ethical sed blue bottle nihil letterpress.

Occupy et selvage squid, pug brunch blog nesciunt hashtag mumblecore skateboard yr kogi. Ugh small batch swag four loko. Fap post-ironic qui tote bag farm-to-table american apparel scenester keffiyeh vero, swag non pour-over gentrify authentic pitchfork. Schlitz scenester lo-fi voluptate, tote bag irony bicycle rights pariatur vero Vice freegan wayfarers exercitation nisi shoreditch. Chambray tofu vero sed. Street art swag literally leggings, Cosby sweater mixtape PBR lomo Banksy non in pitchfork ennui McSweeney's selfies. Odd Future Banksy non authentic.

Aliquip enim artisan dolor post-ironic. Pug tote bag Marfa, deserunt pour-over Portland wolf eu odio intelligentsia american apparel ugh ea. Sunt viral et, 3 wolf moon gastropub pug id. Id fashion axe est typewriter, mlkshk Portland art party aute brunch. Sint pork belly Cosby sweater, deep v mumblecore kitsch american apparel. Try-hard direct trade tumblr sint skateboard. Adipisicing bitters excepteur biodiesel, pickled gastropub aute veniam.

[^1]: Texture image courtesty of [Lovetextures](http://www.lovetextures.com/)
