<h1><div align="center">User Guide for extracting SmartBay Simulation Data:</div></h1>
# 0 Document Version
User Guide for utilizing MATSim Simulation Output Data Version 1.0 - updated 2015 May 13
# 1 Introduction
<p>We describe a process to extract useful information from the output data for agent-based microsimulation software MATSim. The output includes daily activity chains and executed travel patterns for a given population on a given network.</p>
The group maintains all relevant data files at [http://smartcities.berkeley.edu/smartbay](http://smartcities.berkeley.edu/smartbay)

# 2 Description of Files

<p><b><font size="4">2.1.Network File</b></font>
<br>The network file is located at [SF_ Bay_detailed.xml](http://smartcities.berkeley.edu/smartbay/SF_ Bay_detailed.xml).
It represents all major freeways and arterials in the nine counties comprising the San Francisco Bay Area (namely Alameda, Contra Costa, Marin, Napa, San Francisco, San Mateo, Santa Clara, Solano and Sonoma). The network is formed of nodes and links and contains 564,368 links and 352,012 nodes. Nodes are defined through id and location coordinates while link is defined through id, nodes connected and traffic attributes like free flow speed, capcity, number of lanes and allowable modes. A sample screenshot for a network file is:</br></p>
<pre align="justify">&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;!DOCTYPE network SYSTEM "http://www.matsim.org/files/dtd/network_v1.dtd"&gt;

&lt;network name="example"&gt;
    &lt;nodes&gt;
        &lt;node id="0" x="505046.8125" y="137967.7969" /&gt;
        &lt;node id="1" x="520580.9063" y="147882.7969" /&gt;
        &lt;node id="2" x="594615.5" y="199259.2969" /&gt;
        ...
    &lt;/nodes&gt;

    &lt;links capperiod="01:00:00" effectivecellsize="7.5" effectivelanewidth="3.75"&gt;
        &lt;link id="0" from="0" to="1" length="6243.0" freespeed="27.77777777777778" capacity="4000.0" permlanes="2.0" oneway="1" modes="car" /&gt;
        &lt;link id="1" from="1" to="0" length="6243.0" freespeed="27.77777777777778" capacity="4000.0" permlanes="2.0" oneway="1" modes="car" /&gt;
        &lt;link id="2" from="1" to="2" length="949.0" freespeed="33.333333333333336" capacity="4000.0" permlanes="2.0" oneway="1" modes="car" /&gt;
        ...
    &lt;/links&gt;
&lt;/network&gt;
</pre>
Source: [http://www.matsim.org/node/609](http://www.matsim.org/node/609)

<p><b><font size="4">2.2.Population File</b></font>
<br>The population file is is located at [plans_500k.xml](http://smartcities.berkeley.edu/smartbay/plans_500k.xml). It contains a list of daily activity chains for 500,000 agents in the population. A plan is defined by a person id, a list of activities to be performed at various locations at various times and the available modes for that person to reach each activity location. A sample screenshot for a population file is:</br></p>
<pre class="listing">&lt;?xml version="1.0" encoding="utf-8"?&gt;
&lt;!DOCTYPE plans SYSTEM "http://www.matsim.org/files/dtd/plans_v4.dtd"&gt;

&lt;plans&gt;
    &lt;person id="1"&gt;
        &lt;plan&gt;
            &lt;act type="home" x="20" y="-5" end_time="06:00:00"  /&gt;
            &lt;leg mode="car"  /&gt;
            &lt;act type="work" x="80" y="5" end_time="16:00:00"  /&gt;
            &lt;leg mode="car"  /&gt;
            &lt;act type="home" x="20" y="-5"  /&gt;
        &lt;/plan&gt;
    &lt;/person&gt;
&lt;/plans&gt;
</pre> 
Source: [http://www.matsim.org/node/609](http://www.matsim.org/node/609)

<p><b><font size="4">2.3.Counts File</b></font>
<br>The counts file is located at [counts_SF.xml](http://smartcities.berkeley.edu/smartbay/counts_SF.xml). This file contains ground-truth information about hourly counts on certain links in the network. This file is used to compare simulation results to real values but is not mandatory for running the imulation. A sample screenshot for a counts file is:</br></p>
<pre class="listing">
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;counts xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="http://matsim.org/files/dtd/counts_v1.xsd" name="IVTCH" desc="ASTRA_and_ZH_stations" year="2005" layer="0"&gt;
  &lt;count loc_id="111780" cs_id="ASTRA001"&gt;
    &lt;volume h="1" val="14.83"&gt;&lt;/volume&gt;
    &lt;volume h="2" val="4.62"&gt;&lt;/volume&gt;
    &lt;volume h="3" val="2.49"&gt;&lt;/volume&gt;
    &lt;volume h="4" val="1.93"&gt;&lt;/volume&gt;
    &lt;volume h="5" val="5.38"&gt;&lt;/volume&gt;
    &lt;volume h="6" val="12.70"&gt;&lt;/volume&gt;
    &lt;volume h="7" val="52.78"&gt;&lt;/volume&gt;
    &lt;volume h="8" val="156.86"&gt;&lt;/volume&gt;
    &lt;volume h="9" val="159.99"&gt;&lt;/volume&gt;
    &lt;volume h="10" val="156.34"&gt;&lt;/volume&gt;
    &lt;volume h="11" val="187.67"&gt;&lt;/volume&gt;
    &lt;volume h="12" val="224.57"&gt;&lt;/volume&gt;
    &lt;volume h="13" val="208.28"&gt;&lt;/volume&gt;
    &lt;volume h="14" val="219.92"&gt;&lt;/volume&gt;
    &lt;volume h="15" val="247.27"&gt;&lt;/volume&gt;
    &lt;volume h="16" val="268.12"&gt;&lt;/volume&gt;
    &lt;volume h="17" val="303.67"&gt;&lt;/volume&gt;
    &lt;volume h="18" val="368.89"&gt;&lt;/volume&gt;
    &lt;volume h="19" val="288.11"&gt;&lt;/volume&gt;
    &lt;volume h="20" val="168.45"&gt;&lt;/volume&gt;
    &lt;volume h="21" val="102.43"&gt;&lt;/volume&gt;
    &lt;volume h="22" val="66.99"&gt;&lt;/volume&gt;
    &lt;volume h="23" val="55.99"&gt;&lt;/volume&gt;
    &lt;volume h="24" val="37.84"&gt;&lt;/volume&gt;
  &lt;/count&gt;
&lt;/counts&gt;</pre>
Source: [http://matsim.org/node/614](http://matsim.org/node/614)

<p><b><font size="4">2.4.Config File</b></font>
<br>The config file is located at [config_BA.xml](http://smartcities.berkeley.edu/smartbay/config_BA.xml). This file defines the network and population files used for running the simulation as well as other simulation parameters like number of iterations, how the simulation scores are calculated, etc. A sample screenshot for a config file is:</br></p>
<pre>
&lt;?xml version="1.0" ?&gt;
&lt;!DOCTYPE config SYSTEM "http://www.matsim.org/files/dtd/config_v1.dtd"&gt;
&lt;config&gt;

    &lt;module name="network"&gt;
        &lt;param name="inputNetworkFile" value="&lt;path-to-network-file&gt;/&lt;filename&gt;.xml.gz" /&gt;
    &lt;/module&gt;

    &lt;module name="plans"&gt;
        &lt;param name="inputPlansFile" value="&lt;path-to-plans-file&gt;/&lt;filename&gt;.xml.gz" /&gt;
    &lt;/module&gt;

    &lt;module name="controler"&gt;
        &lt;param name="outputDirectory" value="&lt;output-directory&gt;" /&gt;
        &lt;param name="firstIteration" value="0" /&gt;
        &lt;param name="lastIteration" value="10" /&gt;
    &lt;/module&gt;

    &lt;module name="planCalcScore" &gt;
        &lt;param name="activityType_0"            value="dummy" /&gt;
        &lt;param name="activityTypicalDuration_0" value="12:00:00" /&gt;
    &lt;/module&gt;

    &lt;module name="strategy"&gt;
        &lt;param name="maxAgentPlanMemorySize" value="5" /&gt;

        &lt;param name="ModuleProbability_1" value="0.9" /&gt;
        &lt;param name="Module_1" value="ChangeExpBeta" /&gt;

        &lt;param name="ModuleProbability_2" value="0.1" /&gt;
        &lt;param name="Module_2" value="ReRoute" /&gt;
    &lt;/module&gt;

&lt;/config&gt;
</pre>
Source: [http://matsim.org/node/696](http://matsim.org/node/696)

<p><b><font size="4">2.5.Events File</b></font>
<br>The events file is located at [run0.10.events.xml](http://smartcities.berkeley.edu/smartbay/run0.10.events.xml). This file is a standard output from a MATSim simulation. It stores all relevant information (time, link and agent involved) for 7 kinds of instances during the simulation:
</br></p>
1. ActivityEndEvent: Is created when an agent has just ended an activity. (Attributes:getTime(), agentID, linkID, acttype)
2. ActivityStartEvent: Is created when an agent has just started an activity. (Attributes:getTime(), agentID, linkID, acttype)
3. AgentArrivalEvent: Is created when an agent has arrived at an activity right before the activity starts. (Attributes:getTime(), agentID, linkID, legmode)
4. AgentDepartureEvent: Is created when an agent has just ended an activity and is going to depart from the location where the activity took place. (Attributes:getTime(), agentID, linkID, legmode)
5. AgentWait2LinkEvent: Is created after an agent has departed from a facility. Afterwards the agents has to wait until there is enough space for its vehicle on the link before entering the link. (Attributes:getTime(), agentID, linkID)
6. LinkEnterEvent: Is created after an agent has just entered a link. (Attributes:getTime(), agentID, linkID)
7. LinkLeaveEvent: Is created after an agent has just left a link. (Attributes:getTime(), agentID, linkID)

Source: [http://matsim.org/docs/tutorials/8lessons/output/events](http://matsim.org/docs/tutorials/8lessons/output/events) 
<br>All relevant information can be extracted from an events file using EventHandler File (see section 2.6).</br>

<p><b><font size="4">2.6.EventHandler File</b></font>
<br>An  eventhandler file is used to extract relevant information about any event that occurs during the simulation. To implement an eventhandler, we need to write a java class which implements a particular EventHandler interface. Then, we need to create an instance of our handler class and add it to our events instance. An example of an implementation of an eventhandler to determine the total number of arrivals and departures during the simulation is:</br></p>
<pre class="listing">
import org.matsim.core.api.experimental.events.AgentArrivalEvent;
import org.matsim.core.api.experimental.events.AgentDepartureEvent;
import org.matsim.core.api.experimental.events.handler.AgentArrivalEventHandler;

import org.matsim.core.api.experimental.events.handler.AgentDepartureEventHandler;

public class TripCounter implements AgentDepartureEventHandler, AgentArrivalEventHandler {
  private int departureCount = 0;
  private int arrivalCount = 0; 
  @Override
  public void handleEvent(AgentArrivalEvent event) {
	arrivalCount++;
  }

  @Override
  public void handleEvent(AgentDepartureEvent event) {
    departureCount++; 
  }

  @Override
  public void reset(int iteration) {
	departureCount = 0;
    arrivalCount = 0;
  }
}
</pre> 
Source: [http://matsim.org/node/601](http://matsim.org/node/601)
<br>An example of an eventHandler to extract the counts on each link in the network in 5-minute intervals is located at [linkFLowCalculator.java](http://smartcities.berkeley.edu/smartbay/linkFlowCalculator.java). This can be executed using the file readEvents.java.

<p><b><font size="4">2.7.readEvents File</b></font>
<br>An  readEvents file is located at [readEvents.java](http://smartcities.berkeley.edu/smartbay/readEvents.java). It used to create an instance of the eventHandler class and execute the operation. An example of the readEvents file for the TripCounter linkHadler class created in section 2.5 is:</br></p>
<pre class="listing">
import org.matsim.core.api.experimental.events.EventsManager;
import org.matsim.core.events.EventsManagerImpl;
import org.matsim.core.events.MatsimEventsReader;

public class ReadEvents {
  public static void main(String[] args) {
    // The filename of the input file. Point this to the location where your event file is.
    String inputFile = "output/ITERS/it.10/run0.10.events.xml.gz";
    
    // Create an EventsManager instance. This is MATSim infrastructure.
    EventsManager eventsManager = EventsUtils.createEventsManager();
    // Create an instance of the custom EventHandler which you just wrote. Add it to the EventsManager.
    TripCounter handler = new TripCounter();
    eventsManager.addHandler(handler);
 
    // Connect a file reader to the EventsManager and read in the event file.
    MatsimEventsReader reader = new MatsimEventsReader(eventsManager);
    reader.readFile(inputFile);

    System.out.println("Events file read!");

    // Print the counts from the TripCounter
    handler.printCounts();
  }
}
</pre>
Source: [http://matsim.org/node/601](http://matsim.org/node/601)
<br>An example of a readEvents file for the linkFlowCalculator class is called 'readEvents.java'.

# 3 Steps for extracting information from SmartBay Simulation Output
1. Install relevant software and dependencies (see [http://matsim.org/docs/tutorials/8lessons/installation/software](http://matsim.org/docs/tutorials/8lessons/installation/software))
2. Open Eclipse. Click File -> New -> Java Project. Name it for example 'smartBayExtract'.
3. Reference MATSim to this project: <ul type="circle">
4. In Java Settings, click the tab Libraries.
5. Click Add JARs.
6. Select the matsim-0.5.x folder.
7. In this folder select the jar file matsim-0.5.x.jar.
8. Click OK twice.
9. Click Finish</ul>
10. Copy the input files to your project: <ul type="circle">
11. Download the population file plans_ 500k.xml, the network file SF _ Bay _ detailed.xml, the counts_ SF_ Bay.xml and the config file config_BA.xml
12. copy them to a folder called "input" within the java project</ul>
13. Write your custom linkHandler class: <ul type="circle">
14. Right click on the java project smartBayExtract.
15. Click New -> java class.
16. Name it for example 'linkHandler1.java'
17. Write the body of linkHandler1.java as per your requirements (see section 2.6)</ul>
18. Use the readEvents file to execute the handler: <ul type="circle">
19. Right click on the java project smartBayExtract.
20. Click New -> java class.
21. Name it 'readEvents.java'
22. Copy and paste the contents of 'readEvents.java' from the source to this file
23. Make appropriate changes as per your linkHandler class.
24. Run readEvents.java
 

 
