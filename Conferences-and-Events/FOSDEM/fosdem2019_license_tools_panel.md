- This is an unofficial transcript from [Making Sense of so many License Compliance Tools][1] panel discussion at [FOSDEM 2019][2].

- This transcript is licensed under the [Creative Commons Attribution 2.0 Belgium Licence][3].

- The time stamps are in HH:MM:SS:FF format where HH, MM, SS, and FF are hour, minute, second, and [CDDA][4] frame, respectively.

- This transcript has a lot of blanks (denoted by "____") and errors. If you are interested in improving this transcript, please send in your pull requests. Thank you in advance.

# Making Sense of so many License Compliance Tools

Bradley Kuhn: So, this is our panel on making sense of license compliance tools. And, I’m going to ask … I’m moderating. My name is Bradley Kuhn from the Software Freedom Conservancy. **So, I’m going to start off and ask each panels to introduce yourself no more than thirty seconds each, who you are, where are you affiliated with, and what are your relationships with license compliance.**

Thomas Steenbergen: OK. So, my name is Thomas Steenbergen. I work for HERE Technologies. We are part of team behind Open Source Review Toolkit. I’m also involved in SPDX. And I’m also involved in ClearlyDefined.

Valerio Cosentino: Hello, I’m Valerio Cosentino, software developer at Bitergia. So, Bitergia basically creates a development analytics for open source. And … so, I just started to playing with … extracting licenses from code. So, this is why I’m here.

Max Sills: Hey, I’m Max Sills. I’m head open source attorney at Google. I manage our in and outbound compliance processes, and … just recently joined the board of the ACT, Linux Foundation.

Philippe Ombredanne: My name is Philippe Ombredanne. And I’m both the maintainer of a tool called Scancode, which is a license detection tool, and several other open source license compliance utility tools, and CTO for a small software company called NexB.

Michael Jaeger: Hey, my name is  Michael,  Michael Jaeger. I’m, along with other people, I’m a maintainer for FOSSology, which is a Linux Foundation project, scanning for licenses. And SW360, which is an Eclipse Foundation project, providing component inventory. I’m employed at a German engineering company called Siemens. And in my free time, I ____________ trainings about tools.

00:01:50:45  
Bradley: OK, so, let’s just leave the mic at each end, and in that way we all minimize the mic passing. **So, first question for the panel is “what GPL or other license compliance problems can do you believe that compliance tools can solve for users?”**

Michael: Did you say what GPL and other compliance problems?

Bradley: Any of licenses. I didn’t mean … you know, I’m obsessed with the GPL so I’m going to focus on that. But any … any license compliance problems. Any. What’s your laundry list of license compliance problems you believe tools can solve and how do they solve them?

Michael: Actually, I see it today that GPL, since you have named it, is not a problem for most organizations. And if you see it, we are really asking like what’s your problem actually with GPL. We have more problems like on our … on some FOSSology server on some instance maybe … we have fifty packages, which contain these clauses like “This is proprietary information. This is confidential information. This is a file that you need to have the written permission of the copyright owner.”, like files which slipped into open source projects, accidentally maybe. Maybe some of these famous cases have been solved. But still we have, like a past few years, we have experienced fifty cases of files, which are just not for commercial use according to their licenses.

Bradley: How does the tool help people actually comply with all these requirement?

Michael: Well, you scan it and then you find it out that it’s actually part of the open source distribution and you are probably compiling it in your product if you didn’t really look for it. So, I think that’s probably one of the benefits of FOSSology that tries these licensing relevant statements, which prohibit you from commercial use.

Bradley: So, it’s really about discovery. It’s how people discover what licenses are there so they can read them and comply.

Michael: Right.

00:03:39:55  
Bradley: OK. Philippe?

Philippe: To me, the biggest problem is that most of us don’t know what third party code to use. And … as well as it sounds, it’s a bit like if you were building car, but you forget where you bought the engine from and where the brakes were coming from. And that’s still the case. The value of the tools is helping you figure out where the code come from. __________ code. That’s the first thing. And then, what’s the license? And pretty essential things to know before being able to use any bits of code, whether it’s proprietary or free, libre, and open source software, which of a point of view you are coming from. If you don’t know that, it’s like a bit crazy. But we are still very much at the basics these days.

Bradley: Right. So, it sounds like your answer is very similar to Michael’s, that it’s about discovery. Tools help you discover what’s there.

Philippe: Yeah. So, not only but that’s the essential.

00:04:37:55  
Bradley: OK. Max?

Max: Yeah. _________ you.

Bradley: I’m supposed to be the impartial moderator.

Max: I don’t think tools really do a good job of compliance. And I think there is this … this fantasy, or I guess this is industry’s push towards tooling, like let’s just get the best tooling, let’s use the best system and not worry about open source compliance as kind of a substitute for knowledge. So, tooling is really great at a start, for example like when you want to see what the license of some source code is. But it doesn’t work without some knowledge of how to actually interpret the terms of the license, or a thoroughly documented process for building software. How do you build the software? Where do you store the code? Do you … basic stuff like what’s the linking style or something. Yeah, that was I was going to say. I think that there’s like fantasy out there.

Bradley: In my efforts to be an impartial moderator, I’ll push back that a little bit. I think the other two panels who’ve already answered would say, but discovery is the first step. **You’ve got to discover what’s there first to be able to do any of the stuff you talked about. Would you agree with that? Or disagree with that?**

Max: Yes, discovery is definitely the first part. But I guess there’s two camps of tooling. There’s like … So, Scancode is a wonderful tool. We use it extensively. There’s the camp of tooling that wants to use scanning and tooling as an input to a larger process like you’ve talked to people. Human being have agreed on social behaviors around code. And there’s the camp like the Black Duck people and the … like the compliance industrial complex, where it’s … let’s use tooling as a substitute for thought. Let’s not even investigate the software that we are doing. So, I think the first camp, it can be very helpful. But I would agree that it is.

00:06:24:15  
Bradley: So, what do you think tools … what license compliance issues do you think tooling can help with and how does that help?

Valerio: OK. So, I’m pretty new with the licensing things. So, the tool we have, we are working on, basically tries to use exsiting tools like Scancode or Nomos. And they tell us a story about licenses. So, _________ the evolution of license. ______________ all the software development things, like … maybe you move from a private repository to GitHub, so then you have a license change there. So, the idea is to study the evolution of licenses, and see what we can tell about this. So, it’s like … we are like not really focusing on extracting the current status of the project, but more like analyzing and understanding why license can change and the impact on the things that are related to software development.

Bradley: So, dig a little deeper on what you mean by evolution. So are you talking about when other people have contributed under different licenses on top of other ones? That sort of thing? What else in there?

Valerio: When you have like an update on a license, for instance you _______ from GPL2, GPL3, or things like that. Or, maybe you are integrating a component from another open source project that is under different license. So, you don’t discover this at the very beginning. But then, over the time, you see that maybe that component changed the license and this can cause problems in your … So, it’s more like a tracking of like … I mean, there are story about the license you are … or license in your project.

Bradley: OK. So, same question. What can tooling can do to help understand and comply with licenses and how do they do it?

00:08:08:00  
Thomas: So, well, I see it … So, I sort of ____________. We are now developing all in CI/CD. We are going faster and faster and faster. And what I always see is that compliance tooling is _____ way behind we are developing tools by default. So, our focus has been, and one of the challenges basically, we use package managers. All ______ use package manager. In my company, we use close to 40 of them. So, we have more and more _________ CI/CD. So everything faster. We have more of package managers that are not supported by any tools. So, discovery is limited. But then, also when you have all of the information _______ all there tools and all the things, you need to ________ process it. And that’s where we focus on is basically, “OK, we discover. But also then how can you process it?” ________ at Max’s comment, we don’t say we automate anything, I can ________ you cannot automate compliance fully. We call a system highly automated. So, what I do, my best do, is to basically, as Max is lawyer, and our lawyers, is figure out how we can take Max’s effort for the simple cases, and write that into computable rules. But then from the other side, what you do as a developer, in your source code also like, “give you way to indicate this is documentation, this is source, this is examples, and then also get us also in computable form, and make handshake so I can reduce the work of the _______ both side because of handshake, and I generally call as having cats and dogs talk each other, being the dogs _____ be developers and cats mean lawyers and they don’t speak same language. So, my job … I would _______ making the language that they can speak so that it’s easier and we can move faster, and so that the lawyers can focus on the really complicated cases, which really require dedicated attention. So we take the nitty-gritty work which hand out of equation, and just ______ lawyers, “hey, _____, I have something _____ I don’t know. And if we can that automated, which is usually a months long discussion because things are complicated in law. We try to automate as best as possible to give hints. That’s basically what tooling can help you of taking the general discussions that you have, and take it out and focus on really specific edge cases. That’s what we are focusing in.

00:10:25:45  
Bradley: That leads me well into my next question, which will start and go the other way ____. So, this is an old phrase in computing “garbage-in garbage-out”. Usually say today something like faulty data set, or something like that. I would argue, be a little bit un-impartial here, almost every free software project out there is a poor data set for understanding its licensing. Developers, as you pointed out, do not do a great job at expressing their licensing intent in a way that is consumable and automatable. There are efforts out there to try to get developers do this. Personally, I believe that … as Alexios’s talk years ago was since _____ is happy because there’s always going to be this pushing this rock up a hill and developers are not going to want to follow any specific documentation system of licensing. So, given that, how can tools actually work in a real way, to even to discovery, let alone anything else, **if all the data is so bad that files inappropriately annotated, projects are inappropriately annotated with licensing, how can we actually solve that problem in an automated tooling way when the data is that poor?**

Thomas: So, the solution we came up with is … Well, it’s actually, we have multiple parties from multiple backgrounds working together. So, just to explain this whole panel for people … There’s actually a group of people that are working together. So, how it works is that open source _______ actually uses this kind of __________. So, we use actually use that __________. We can then basically what generate … we generate data done. We translate _____ into SPDX, which is _________. And then basically, Michael can basically ingest in FOSSology. So, the solution that we are working on is having all this various open source tools work together.

Now, there are a lot of companies and this is, maybe, different from developers. Companies have liabilities. So, companies care about licensing of open source. You as a developer might not, but your company does. So, the way how we work is basically companies have these huge problems ____________  CI/CD. Everything goes faster. And we have this data problem. So the solution how we came together is by all organizations that have this problem working together. And this is why we founded last year, we founded ClearlyDefined, which is basically a center of repository where we can take all of these data in, and have a curation _______ on top, and then fix it. All of the companies pretty much to do anything ________ compliance have compliance team that do nothing else to figuring out these licenses. They used to keep all of these data inside. And the we are like hmm, we spoke, and so Jeff McAffer and I spoke a year ago. And it’s like, “why? Why? We are all doing the same work.” So, what we now see is basically all these companies realize like we have no proprietary information this. We are all doing the same work. Why not collaborate? And then, basically take this … fix this data again together. And that’s how we know our duties because basically in case you have noticed open source is exploding. That’s becoming more more more. We ____ more more package managers. Everything has to go faster and faster. If we don’t solve this, basically companies well might say, like, we will not use your open source project simply because your licensing is so bad that it takes me too much effort to push it to our development tool chain. Even if it’s a great piece of open source, we will not use it because your licensing is so ______.

So, that’s why now we are trying to work together, all the people ___________. Yeah, Max, as well, __________ in ClearlyDefined, to basically what can we do to provide tooling and work together that we can lift the whole community to fix … Again , we don’t want to impose you how to do licensing and then force the rules to your throat. What you will see is basically as we’re working together, and we will follow pull request from saying, “Hey, could you note please fix this. You will have to pull-request, please.”

00:14:28:25  
Bradley: So, let’s pass along. So, it sounds like your pitch is that you’ve solved that all, there’s no problem with compliance any more. All the upstream … Well, we have a plan. Right? And it’s going to be all upstream ______. What’s the date it’s going to be done by?

Thomas: We are already right. It’s so good.

Bradley: **OK. So, his argument is it’s done today. You go to ClearlyDefined, every open source project that matters you can get all the information. Does the whole panel agree with this?**

Thomas: No, no, no. It isn’t possible. There are so many open source projects out there. We started working on a solution. So, this is basically … always _________ foundation. Dozens of companies that …

Bradley: OK. So, pass mic on. Do you think this solution is going to work? Give me the date. When do you think all upstream projects are going to have perfect licensing information such that all this tooling perfectly tells you everything? Give me the day when you think it’s going to happen.

Valerio: __________ solution, I give the date.

Bradley: OK. Well, do you agree? Do you agree or disagree with the solution? Let’s pass along. Do you agree with this solution? And if so, what’s the date it’s going to be done by?

Valerio: __________ important. But data is _______ about. But we are integrating the different tools altogether, and trying to get the information also from _______ sources _______. But I would not bet on the date.

Bradley: So, Max, what do you think? Do we have … _______ going to get ______ perfect?

Max: No. This is impossible. So, let’s talk about why that is. The input data will always be garbage, for the rest of time, because the law - copyright law is garbage. That’s the problem. The … And I will just say this, “Who knows what the derivative work is? Who knows, unambiguously and every case, whether a piece of code A is the derivative of piece of code B?” No one knows. No one knows. And no one can know. Everyone has to do their own risk analysis. And this is the human factor, which is the only thing, I mean, tooling will help. But I think we are in this kind of obsessive compulsive phase like you were saying a second ago where we have these idea to fix copyright law once and for all if we only could have annotations and a specific meta data format at … on a header of every file, then derivative works wouldn’t be a problem anymore, then we ignore the copyright ________ and everything. Forget derivative works. Who can analyze whether something is even protected by copyright? And so we are always going to have these … or whether it’s purely functional, like that is actually still _____ area of law, still actively developing. So, never. It will never happen. But we can … To your point earlier, if we are integrating our license scanning tools, in … as part of development process, that’s really the important thing, because we keep it open and we keep that tightly integrated, and how people are storing source and actually developing programs, because, again, once you’re … a lot of people don’t want to get their hands dirty, a lot of attorneys don’t want to get their hands dirty with software development. But if you are looking at it after the things are already compiled or even distributed to someone, it’s really impossible to figure out what’s going on.

00:17:24:39  
Bradley: What about you, Philippe? Do you think we can fix the upstream data problem, and if so when?

Philippe: Actually, it’s going to be fixed on … December 31st, 3000. Exactly. Right before midnight. No, no. But it’s impossible to fix. Yet, there are things which are practically possible. And contrary to what you said, you can have developers participate in process and help. So, I have two practical examples. First is Linux. I’ve been involved with some of the top level maintainers of the kernel for the last two plus years with others to help clarify the licensing of the kernel. And weirdly enough … Not weirdly enough, it’s an old code base. It has a lot of history, probably the largest number of contributors we’ve ever seen in any free, libre, and open source project. When we started, there were about 80 different licenses. And just for the GPL, about 700 different ways to state this file is under the GPL. And, you know, there’s a limited number of words to express that. But nevertheless, you could think about every single permutation and it _____ at some ______ of time in the kernel code base. So, what we are doing is scanning and reviewing in details. I’ve just finished another review of the _________ yesterday. Every _______ the kernel to decide what’s the correct license, is it clear-cut or not, and how can we replace any boilerplate by SPDX license identifier one by one. That’s huge amount of work. We are hoping maybe by 2019, under current push to have maybe 60 percent of the files covered there. And there are still a lot of ambiguities. And really weird stuff where, as time goes by, companies have disappeared, people have died. And if you have ambiguities, especially __________ Linux where some part of these trees ends up in old non Git trees, and whether in the BitKeeper, it’s a mess. Nevertheless, you see, now ____, if you watch the LKML, the Linux Kernel Mailing List, developers diligently providing simpler and clearer statements of the licenses they could contribute. And other maintainers nagging them to do that. So, there is a progress there.

Bradley: I think we are all for ____. I agree with you. I think I’m all for expressing licenses more clearly by __________ question on the Linux plane. **So, what happens when you can’t represent the license of a particular set of copyrights with a simple SPDX expression?**

Philippe: Yeah, so, the problems is … it’s not really about SPDX. What if the license is ambiguous? And there’s still a good number of files, which have ambiguous licenses. And eventually, there are two ways whether you can get back to the original contributors and trace it back unambiguously and clarify the thing, or you have to get rid of the code.

Bradley: I agree with that, too. But when it is unambiguous, you know what the license is, but you just can’t write an SPDX expression for it, what do you do?

Philippe: I don’t think … so … Why would not you be able to do that?

Bradley: Because the … there’s an exception involved, that doesn’t have an SPDX identifier, things like that.

Philippe: Yeah, well, so, you can still write an SPDX expression for that. And eventually, if there’s no official identifier at SPDX for this ____________ new exception, then you can ask for it to be added.

Bradley: And if SPDX says no, what do you do?

Philippe: Well, you can continue to use it as private identifier. I mean, just to give you an idea, there’s about 300 _______ licenses which are referenced at SPDX. Scancode detects about 1,300, about thousand more. And it doesn’t mean you can just trash them and ignore these licenses.

Bradley: So, that’s … SPDX recommends that people, if there’s a missing identifier, they just make up a private space and …
  
Philippe: And eventually, this discussion to have decentralized name spacing to address that.

Now, another example, which is I’ve taken the top thousand  packages of several popular application package manager, namely JavaScript with npm, RubyGems for Ruby, PyPI for Python, Maven for Java, and Nuget for C#. And computing a bunch of statistics on the clarity of licensing, it’s still in progress, not finished. And there is one interesting __ bit of that ____ came up, which is, weirdly enough, the licensing of Node package, that means JavaScript, which are more often smaller and more recent than others, is usually clear. And, one of the reason I think it’s clear is it’s not so much has to do because it’s more recent code or smaller package in general, but because there’s been significant effort of the JavaScript and Node community, to ensure that there’s feedback provided by developers. If you submit a package to be uploaded to the npm registry, and you don’t have a proper SPDX license expression attached to your package, you’ll get warning. It’s not rejected, but you get warning. And, my only explanation for this difference between Node and other package managers is possibly based on that. So, I think if you provide feedback, and provide some information to software developers that license is missing or license is not clear, they will act. So, if you go even further, eventually for the kernel with Git check batch, which is the tool used to verify each pack is correct before you submit it, act as quasi license compiler. And if you treat licensing as something which is as important as the code being able to run in compiler …

00:23:24:13  
Bradley: I _______ question. I want to get Michael one chance to answer my previous question, which is when and how do you think the upstream data problem can be fixed and …

Michael: OK. OK. So, you don’t forget about the data. Actually, I’m asked about dates all week day. So, I was hoping on weekend I won’t be asked on dates as a project manager. But the answer is something like Philippe has answered. I think the question is similar to when will we all have electric cars. And the point is at no point of time because there are some who adopt electric cars very quickly and there are some who just don’t care. And I think there is some area in open source where people are just not so very interested in publishing license clean … clearly defined packages and they stay around, and will also stay around because today open source projects themselves have a lot of dependencies. And if they don’t update their dependencies, they hang around for five or ten years. You will find very super famous Java components with ten year old dependencies. And then you can ask them, or maybe you contribute something to update their dependencies, but unless all the dependencies are out there, being used by open source software, not really being clearly defined in terms of licensing, you will have the situation and it will be electric cars. In 2040, the majority of cars will be electric, but you will have combustion engines hanging around. And I think, the electric cars analogy is very interesting because the same thing happens on license compliance. There are different players trying to come out with their own solution. Right? We have the Linux initiative here. We have Reuse.software from the Free Software Foundation Europe. Or, we already have FOSSology where … for example my employer, one of the reasons why we invest into FOSSology is because we think if tools are freely available. At the time when we have started to contribute FOSSology, there were not so many license compliance tools out there. But we thought if a tool is actually available as free software, it will help to clean up licensing and open source software.

00:25:22:23  
Bradley: So, that actually _______ to the question, third question __________. Let me start with you and move … No, let me start there and _____. But it picks up when you were saying last _______. So, I once called upstream license … license annotation in projects an unfunded mandate upstream because from my point of view that companies are asking for this. They want perfect upstream annotation of all the licensing to make it easy so ____ tools work well, and give all this data. But upstream developers, they have other work to be doing. They are trying to this software work. Making perfect license annotation in their project is a big job. And, often I … it sounds like the tool folks are saying, “well, let’s collaborate with you get it right.” How much do you think the obligation is really on the folks who want this annotation to get into their projects, do the annotation for them and offer it as patches to them and say, “does this look like to you … use it versus this collaboration I ___ talking about, which sounds … **it sounds interesting. But on the other hand, it’s really unfair to ask these developers to do get another job when it is not they want to do. It’s really the job that people who are all obsessed with this license compliance stuff to actually get it done.**

00:26:33:32  
Michael: Yeah, I agree. I think contributing unambiguous annotations is a good job for those who are actually trying to have that, or want to have that. The point is that in some cases you cannot actually contribute it because you are not copyright owner if it’s ambiguous. Right?

Bradley: We can propose. Right? You can propose I think this is what you meant, and copyright holder accepts and incorporates, then they’ve assented.

Michael: Yeah. I also think it would probably accelerate the entire thing of those people were asking for it, and actually contributing this cleaner work. And I think there are maybe ClearlyDefined also goes into this direction actually because, for example, ClearlyDefined is able to take over analysis work from FOSSology or other tools. Then actually someone else can contribute that to the …

Bradley: What do you think about that, Philippe? Do you think that … Do you think it should be an unfunded mandate upstream, or do you think somebody has the job to come along and do this? And if so, who?

Philippe: So, I don’t think it’s either or or. Unless you live in a parallel universe, using software which … for which don’t know what license terms you need to abide by, it’s just crazy. I mean, the same way, I wouldn’t want to use any software for which I don’t know the license. That’s a gateway.

Bradley: I agree. But the most developers are going to throw the GPL on its up level directory, start making files, and all of us would consider that a fully GPL project. It’s annotated enough for any developer to care about. Probably for any lawyer to care about. But the compliance folks _______ want better annotation. Right?

Philippe: I think it’s perfectly OK for anyone. I don’t care about annotation per se. I care about clarity. And if the convention, and it’s widely accepted as a convention ____, if you strap a GPL at the top level of your project, your project is GPL. Then that’s perfectly good enough. I may not be perfect. It would be better if you were a bit more expressive, maybe state what the license or feature of the files. But nevertheless, that’s better than anything and better in many case than nothing at all that we’ve seen several projects. So, it’s not so much about strapping annotation ______ as much as being able to discover whatever convention, maybe used by a project or communities. The thing is terrible when you get nothing.

00:28:59:15  
Bradley: So, Max, what do you think about this issue, this unfunded mandate question? Should upstream have to maintain this? And if not, who should maintain ______ ?

Max: Obviously, upstream shouldn’t be forced to maintain it. We are all benefited from software. We shouldn’t be imposing … sometimes extreme commercial hardship on them, for something that they gave away for free.

Michael: Well, if you ask it this way, I would agree to _______.

Max: But, I think you made an important point, which is you don’t … You want clear licenses. So, I think … I think that … Things I was going to say was convention really matters here. And I think that’s something that the tooling people is losing, which is that it is a convention that if you put a GPL license at a root level directory that all the other files are going to be under that license. And we’ve lived with that convention. And it’s been really low friction to create a new GPL software, for example, under that convention. And I think what we don’t realize we are doing is every time we do another iteration of the new obsessive, compulsive behavior of documenting and annotating. We were creating social precedent, and we were creating commercial conventions, which if there ever ambiguities in licenses, eventually could be consulted on. So, can you imagine like a project … There’s two project. One is GPL licensed at its root level directory. It has 10,000 files. I could think now I can use it unambiguously. What about when we moved to world where every one of the 10,000 files needs to have a perfect annotation, so is the convention is going to be that if one of those files is missing an annotation, that almost sudden __________.

Bradley: That’s actually … because ___ a lawyer, I’m going to ask you a legal question. And you can’t give us legal advice because you are not a lawyer. But tell me …

Max: I’ll give you a legal advice. Go ahead.

Bradley: Tell me … So, the compliance world has been feeding me back for years that the file … the file on the disk has special significance under copyright that annotating the file with its license is incredibly meaningful. So, can you tell me exactly where on the copyright statute that says that the file on the disk is the special …

Max: Each source file?

Bradley: What’s that?

Max: You are saying each source file?

Bradley: **So, I’ve been looking for years in the copyright statute where it says file on the disk is special and that’s the thing you should annotate with permissions. So, can you help me find it?**

Max: No. It’s not there. Obviously. And actually, I mean, if you really want to freak people at copyright licenses at least _______ need to be written. Right? We can really get freaky with the extent to which convention can start talking about.

Bradley: So, let’s take that a little bit. So, I mean, I’m being a little _____ about the file because file was not … were ___ copyright controls attach. How do we annotate, how do we annotate copyright in a software project? How do we figure out who has copyright or who has _____ license? Where does the copyright attach? Where does the license attach? People have argued that C tokens, like if you tokenize the C program, the copyrights attach with each token. I don’t think there’s any legal backing for that. I think probably _______. So, but, I understand the problem. How do we find where to annotate?

Max: I think the appropriate thing to do is to be respectful of project maintainers. So, if we look at it from the view point of respect, where people have taken an extreme amount of effort and put something out there for benefit. Then we should take project as they come, instead of dictating I think how they should annotate. We should say, “OK. If it’s clear enough that using some kind tool we can scan it. We bear the burden. We bear the cost of assessing the provenance.” Then, that’s probably good enough. We should probably circle around the conventions and don’t impose so many burdens on.

00:32:25:15  
Bradley: So, Michael has already accused me of … I want to give everybody a chance. Let’s keep it. Michael has already accused me of changing the question in the middle. So, just give us the general thought on how you feel about the issue of upstream annotation. Who should do it, why, when, and how?

Valerio: Well, I agree more or less on what they said. So, _______ convention. So, agreeing on some of ____. But, for instance, the … the work that npm for instance is doing on GitHub, so, forcing … forcing. All right? ______ putting warning to _____ licensing your project can help. So, I think it’s like a mix from upstream and then also from knowing what you are doing when you write code. So, I would say that ______.

Bradley: What about you? How do you feel about the upstream annotation question?

Thomas: So, luckily, at my company, I could write a policy on this. And ______ we say like, “Don’t fix the problem on out side just _________ for this because for us, it’s basically if we don’t … if we patch it to ______, so we patch it _______. So, just you know, we do have in our tool _____ ability where we can say ______ convention ____ if ____ license ______ it supplies all the files. It is possible to basically translate convention into machine learning. We try to say like, “Hey, please upstream it.” because for us, it’s basically if we fix it once, it’s basically fix ____ go forward. And sometimes it’s really really trivial things. And it’s like, “Guys, come on. It’s like takes you five minutes to basically to fix it.” We are sometimes talking about … most of the time, licenses are already there, but just because they didn’t perfectly follow how, for instance, Maven specifies _____ how the license _____ because it’s …  yes, it’s in a Maven Ref, but it’s deeply buried _______ there, it’s a five minute fix like just fix it and _____ fixed for the whole community.

00:34:16:25  
Bradley: Good. So, one last question that I want to ask you. Then I’m going to turn to audience. **So, my last question is the biggest compliance problem I see in the world is, under copyleft licenses, the requirement for complete corresponding source code. The source code that corresponds to the binaries, or otherwise, minified JavaScripts, binary-like things. Tell me what tooling helps with that if any, and how.**

Thomas: So, you want to know corresponding source code for …

Bradley: Right. So, you have a binary. Right? I mean, this is the ultimate compliance problem. I have a binary that I know was built from some sources that are under a copyleft license. How do I produce the source release that goes along with it? What’s … what and where is the tooling that helps with that?

Thomas: So, are you the creator of the binary, or you are a consumer because …

Bradley: Either way.

Thomas: So, if you are the creator, basically, what you are trying to do is basically give you the tool chain for free and what else ______ working on is giving you instructions on, “hey, if you do case ______ we basically what we are publishing for all the various package managers, how you can comply with that.” And like, literally, exact details of like, “if you do this, and this. If you are doing Maven, do this. If you are doing npm, is that.” So, those details were not available for _____. Yet most companies have written those. And we are like, when I ask companies ____, “Oh, you have those, can you just open-source _____ ?” And they are like, “No, no, no.” So, now, I basically decided with a couple of other people to we are just going to write them, we anyways have them, publish them as basically this is how you can do it. And all the tools will support that. Yes, it will require some time for some tools are a little bit more complicated to do this. But, yeah … And then, basically, for me to ____, once we have open tooling, and we give you the documentation on, like, this is how we do it. It’s basically us ______ it. Or the company ______ it. It’s going to all the tools that are part of that stack. And basically, filing pull requests and say, “Hey, _______, we would like to ______ this and this. Are you OK with this? And basically we provide the tooling for that.” And then, yeah, it’s going to take a while for ______ all the tools. But, yeah, my solution, we have to, as we are the ones that … we’d like to have it. We have to invest to fix it. So …

Bradley: So, what do you think? What are the tools out there now that help with complete corresponding source code provisioning? On either side, consumer or producer.

Valerio: I have no idea. I mean …

Bradley: I think I agree with you, actually, so, because I haven’t seen the tools yet. I’m trying to find out where they are and how to get them. So, I agree with you. That’s my _____ answer to ______. So, we are to agree. And we are going to leave it. Max?

Max: A miracle is up there. A miracle. So I just want to give a shout-out to the Quartermaster project. It’s a great project. It’s in the development. I think that … Yeah, it’s going to be really hard. But the way to get closer to making sure that when you convey a binary, you convey the complete corresponding source is to make sure that whatever tooling you have it’s really deeply integrated into your build system because that way, you can create a manifest you know the exactly every source file that went into the binary. It can be very easy to convey ______ tool chain.

Now, as a consumer of binaries, like let’s say, you are in a relationship with a company and they give you binary and you are required to re-distribute it. There, it’s … it’s going to be impossible to comply because you are going to do a contract or negotiations. They are going to have to give you source or an offer. You are going to have to pass that along. It’s really … it’s really difficult. But as a producer of a binary, it’s not that difficult as long as the scanning is deeply integrated with build system.

00:37:52:32  
Philippe: To the point, yeah, if you are not the producer of the binary, it’s really hard. Even if you take a package in a popular Linux distribution, being able to ensure that you get the exact corresponding source code is not a given thing. Now, some tools like Quartermaster can help. I also have a tool called Tracecode, which is using “strace” to trace the build and figure out which files may be used. But it’s really very low level help and it’s 100 of the work that’s eventually needed. To me, the simple thing to ensure you always have the corresponding source code available is to always work from source. And it’s something that’s so surprising everybody is using open source, but, very often, we consume package and projects as precompiled binaries coming from left and right. And the software teams, be they open source developers themselves or in commercial context, don’t have the corresponding source code. It’s a real problem, especially after the ____, getting back to the source is going to be harder and harder. Web sites disappear. There is one person and one team that helps to preserve that. That’s the Software Heritage Project, which is trying to index and preserve all the source code. And this is very important. And we don’t realize how important it is. Whole ecosystem like in Java that’s been used to consume only binaries. There is huge amount of Java code, which is not available and no longer available in source code. And once they are available in source code, there is no license information.

Bradley: Yeah. I’m going to agree that everything in the world should be available in source code if it’s software. So, I’m with you on that.

Philippe: Even if you don’t publish it as a consumer, not taking advantage of the fact that the code is available is crazy. It’s just you are giving up on the benefit. Now, getting back to the other question just before, I wanted to add something, which is if you are publishing source code, supposedly under an open source license, you want it to be consumed by somebody else. Otherwise, there is some problem in why you publish source code in the first place. So, I think clear licensing is … should be part of the standard practice.

Bradley: I would argue that we should not optimize for the most pedantic corporate user when we ___.

Philippe: Exactly. And to this, for instance, take two examples. So, practice in the Linux kernel, as always been to always annotate each and every file. So, that’s the common way for Linux. If you take another ecosystem, for lack of better word, Ruby. Ruby developers hate writing any comments in their files. So, there’s very few comment in general. And even fewer license related comments or annotations. So, it would be crazy to force the practice of C and Linux kernel developers on Ruby developers.

00:41:02:45  
Bradley: I do want to get Michael a chance to answer the source code provisioning question. And I’m going to get some audience questions.

Michael: Yeah, because also Tom wants to hold out the sign here. OK. Oh, so, answering this question as the last person is probably redundant because I agree that as a producer. You have Quartermaster there. And there’s Zack from Software Heritage also sitting there, doing an interesting project in this area.

When you have a binary, this binary analysis toolkit might be interesting. I think there is a new generation … version ______ to be published soon, Binary Analysis toolkit Next Generation, BANG. So to say, I think that’s interesting and I think that should be more open source because the old binary analysis toolkit was open source, but database of fingerprints, what you find in binary and associations with source code being published was not public. So, I think that’s going to be changed and I think that’s probably also an interesting tool.

00:42:05:38  
Bradley: So, we are going to take a few audience questions with the last ten minutes, which means we have to share this mic because ________ mics in the room. So, Tom is going to round the mic, and I will pass this around to others. So, if you say who on the panel is going to answer first, that will help.

Attendee 1: **There’s basically one burning question with everything I’ve heard now, which is like in high-potential scenario.** In a big enterprise doing like Java software for ten somewhat years starting to care about license compliance now. It’s like, “OK. Just like break down and ______ whatever ______ you have because basically you are in a very bad place and you are not going to leave soon.” Or like, “What do you do?” because … Everything that you just told me sounds pretty bad, actually.

Thomas: So, you ask what to do? So, you are basically a new company and your ______. So, what I would recommend for Java, Open Source Review Toolkit, my own tool. We were in exactly the same place. And we basically … We looked. So, the difference is basically ________ all the tools. Basically you need a tool that understands package managers. And the trick for all the previous open source tools most ______ just on file level. Corporation ________ analysis. But it didn’t take the package information into account. And so, we basically we really looked at all the … actually, we spent two years looking at all the proprietary ______ out there. And they don’t really work if you ____ look at, if you understand. So, my question for the tools was like how do you get to your source code. So, how do you get what packages are in that? The second question you also have, when you show me concluded licenses, how did you get to that conclusion. These are the two questions that … So, no matter tool you pick, there are two questions you have to ask yourself. So, I …

Michael: Can I add some something to this, something important because I was expecting that he was answering with the tools. But I would answer, even though maintaining tools, situation. You need to become a ______ a few situation. Like what open source software you are using, what is actually your compliance risk, how do you distribute software, what’s your distribution model. And from then on, you probably end up with this ____ likely. And I think there is also Java support in Quartermaster if I’m not mistaken. But I think the first thing is situation. Also when I talk to other companies, want to use FOSSology, it sometimes just turns out it’s not a right tool for them because they are in a different situation and have different compliance needs.

00:44:49:39  
Bradley: OK. Say which panelist do you want an answer ____ you want to have answer question.

Attendee 2: So, I don’t know who is the best panelist to answer. I’m asking about MIT and BSD compliance. So, SPDX identifies the licenses with leaving the copyright year and copyright holder as variables. **So, how do you, with tooling, when the licenses require you to reproduce the specific copyright year and holder, how do your tools deal with that, and as tool makers, how would you like upstream projects to make it easier for you to deal with?** For example, Facebook has, like, fixed year. Google uses like tautological copyright holders, so it says like Chromium authors. And then, maybe, Apache plus LLVM addresses the GPL 2 compatibility in a different way.

Philippe: So, just to rephrase your question is how important is it to have all copyright statements  in order to comply with MIT and BSD license and how important are the years and copyrights?

Attendee 2: How do you deal with MIT and BSD compliance? How would you like upstream projects to … would you like them to do with years and copyright holders so that it is easy to comply with ____?

Philippe: For me, writing tools, that they copyrights is … I like them to be parsible. But I think the bigger question is how important is it to have the exact statement. I remember discussion with a developer from actually Google, working on next version of __________. And they were selling me that it was absolutely essential to have the “All rights reserved.”

Max: No, no, no.

Philippe: Trailing word from copyright statement. That was a pretty big discussion so we can show that. So, I told him, “No. It’s been … It’s over since 1950.” So, the question is also legal question.

Max: I would say as little as possible, like, the Git Log is a great documenter of both the contributor and year. Right? If there is ever any infringement litigation, people would go to that immediately. So, if you can just get rid of all copyright statements in _____, I’d be happy with that.

Bradley: I’d also add the easiest way to comply with copyright notice requirements of non copylefted licenses is treat them like copyleft licenses: Always give the source code to everyone in the world always, and the all the copyright notices we write, just always give everybody source, don’t write any proprietary software, you know, solve all these problems.

00:47:41:70  
Attendee 3: **So, my question is where do I find or where can I get information on what tool might work for me. So, let’s say, I’m a company just setting out on compliance, and I’m wondering what tool can I use.** Now, apart from me telling them these and these and these tools are available and this is what they can do, they might not believe me because while you are lawyer, you don’t know anything about tooling. So, where can I send them?

Bradley: So, I have decided because Max is the biggest consumer of tools on the panel, and there’s too many people who make tools on the panel, I’m going to let Max answer as a consumer of tools.

Max: OK. I think the response is you are asking a wrong question. And we do with this a lot, sometimes more than ______. But if you are looking at a situation where things seem really messy, there’s been a history about practice, the first thing you need to do is talk to people. You need to talk to the lowest level engineers. You need to talk to their management. And before asking for tooling, you need to make sure that there is some kind of coherent process for checking code in. Is there some kind of basic IP training to the employees so they know how they can check code in? Is there code segregation? So, I think your problem is purely human. And then, after you solve the human problem, if you can solve them, then tooling is really … it doesn’t matter what you choose. Every one of these tools is going to help you do what you need to do. But you need to be solving the human problem first.

Philippe: 100% right, I mean, process first! And you can choose my tool afterwards.

00:49:21:55  
Attendee 4: OK. So, let’s assume that we work at a company that is still on the path to putting everything in open source, you have a mix of open source licenses and binary or proprietary things. **Does SPDX or a process using something like that actually grok the fact that some things in their binary or non open source licenses?**

Thomas: So, as a company that still has a lot of proprietary stuff in there, what we do is actually re-make our own license identifiers for all ______. So, we treat basically open source licenses and proprietary licenses as licenses. So, the tool is designed to handle both. And SPDX supports basically also writing your own license identifiers. So, what we do, for instances, is ____________ LicenseRef. So, we do license ref., proprietary, and a year. This is how ________ identifier, and all of our packages, when they go to customers, they will have an SPDX license identifier exactly for _____, our customers, when they insert our packages, they see exactly the licenses.

00:50:34:00  
Attendee 5: OK, I have one last question and that is on this question of complete and corresponding source, I’d like to ask the tools people on the panel. First of all, **are you aware of the Reproducible Builds project?** One. And two, **has that helped you at all in getting to complete and corresponding source?**

Thomas: Yes, we are aware. It is how someone to … The problem is that whole chain is not yet supported to do all of that. So, what you want is … what we would want to have is basically all of this tooling running at software creation, but also be able to parse ______ artifacts created afterwards. So, it has to do the whole tool chain. And for that, that still required a lot of work. It’s like, where we are now _____ open … open tooling is working at source code creation a lot and figuring out discovering and processing that. We are not yet there, _____ really the end-to-end. We’ll get there eventually.

Anyone else want to comment?

00:51:50:00  
Michael: Yeah. I think there are a couple of steps before that, which already solved the problem of providing the complete corresponding source code because I think Reproducible Builds is always producing the same binary with the same signature, or … like hash values. This is step beyond that. And I wanted also to add that I understood Mirriam’s question differently, supposed that you understood the process and you understood your roles. I think there is a problem that we don’t have a central marketing department for open source tools so far. Right? So, people know that there is open source, there are open source tools and license compliance. But it’s really difficult to understand the capabilities of the existing solutions. And there is actually an effort on GitHub. It’s called “Sharing Creates Value”. And there, we would like to list all the open source tools, and explain their capabilities and how they fit together and how they could be arranged in the tool chain in a company or so.

Bradley: So, I’ll take my prerogative as a moderator to say on the Reproducible Builds question, and my very biased view because Reproducible Builds is a conservancy member project. But I thought this before they were a conservancy member project. It is the best things to come along in the last twenty years with regard to the complete corresponding source code problem in my view. So, without ______, I want to thank all of our panelists and many of them, before you clap, I want to let you to know many of them submitted talks of their own. And we cajole them into being on the panel together instead of having their own talks. They were very gracious about it and I would like you to give them a big round of applause.

----
[1]: https://fosdem.org/2019/schedule/event/license_tools_panel/
[2]: https://fosdem.org/2019/
[3]: https://creativecommons.org/licenses/by/2.0/be/deed.en
[4]: https://en.wikipedia.org/wiki/Compact_Disc_Digital_Audio
