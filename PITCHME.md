---?image=assets/images/gitpitch-audience.jpg
@title[EDK_II_OpenBoard_Platform_Porting_pres]
<br><br><br>
<span style="font-size:0.75em" >This slide deck has moved to:  https://gitpitch.com/tianocore-training/EDK_II_Porting_Projects_pres/master#/
</span>
<br><br>
## <span class="gold"   >UEFI & EDK II Training</span>
<span style="font-size:0.85em" >EDK II Open Board Platform Design for Intel Architecture(IA)


<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  EDK II OpenBoard Platform and Porting  

  Copyright (c) 2019, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Define the porting task list for porting existing <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;open platforms in EDK II</span> </li>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Determine the necessary porting for each stage <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&amp; boot phase of a new EDK II open platform project </span></li>
</ul>

---?image=/assets/images/slides/Slide3.JPG
@title[Porting Approach]
### <p align="center"><font color="yellow"><b>Approach – Porting EDK II</b></font></p>


@snap[west span-90 fragment]
<br>
<br>
<br>
<br>
@box[bg-royal text-white my-box-pad2  ](<p style="line-height:40%"><span style="font-size:01.1em" ><b>Find Similar Open Board Projects</b><br>&nbsp;</span></p>)
@snapend


@snap[south-east span-85 fragment]
@box[bg-purple-pp text-white my-box-pad2  ](<p style="line-height:40%"><span style="font-size:01.1em" > <b>Staged Approach by Features</b><br>&nbsp;</span></p>)
<br>
@snapend

Note:

- Many examples of packages in the UDK / EDK II source base 
- Find a similar package or platform or Open Board project that meets target project needs
-  Build description files are text files using basic text editor to update – no GUI with the goal of booting to the UEFI Shell


<!---  Section for Porting Task  -->

---?image=assets/images/binary-strings-black2.jpg
<!-- .slide: data-transition="none" -->
@title[Porting Task List Section]
<p align="center"><span style="font-size:01.25em"><font color="#e49436"><b>Porting Task List</b></span></p>

@snap[north-east span-95 ]
<br>
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%" ><span style="font-size:0.9em; font-weight: bold;" > <br><br> <br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

<!---  col of numbers Gray -->

@snap[north-west span-10 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>&#10102;<br><br><br>&#10103;<br><br><br>&#10104;<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend

<!---  
1
-->


@snap[north-west span-10 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>@color[yellow](&#10102;)<br><br><br>&#10103;<br><br><br>&#10104;<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend



@snap[north-east span-92 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[white](Get the EDK II packages to a local workspace)
<br><br><br>&nbsp;
<br><br><br>&nbsp;
<br><br><br>&nbsp;
<br><br><br>&nbsp;
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>
@snapend


<!---  
2
-->


@snap[north-west span-10 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>@color[yellow](&#10102;)<br><br><br>@color[yellow](&#10103;)<br><br><br>&#10104;<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend


@snap[north-east span-92 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[white](Get the EDK II packages to a local workspace)
<br><br><br>&nbsp;@color[white](Select the Ref and correct Intel® FSP Package)
<br><br><br>&nbsp;
<br><br><br>&nbsp;
<br><br><br>&nbsp;
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>@snapend

<!---  
3
-->

@snap[north-west span-10 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>@color[yellow](&#10102;)<br><br><br>@color[yellow](&#10103;)<br><br><br>@color[yellow](&#10104;)<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend


@snap[north-east span-92 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[white](Get the EDK II packages to a local workspace)
<br><br><br>&nbsp;@color[white](Select the Ref and correct Intel® FSP Package)
<br><br><br>&nbsp;@color[white](Copy a reference <font face="Consolas">OpenBoardPkg/BoardXXX</font> )
<br><br><br>&nbsp;
<br><br><br>&nbsp;
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>
@snapend


<!---  
4
-->

@snap[north-west span-10 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>@color[yellow](&#10102;)<br><br><br>@color[yellow](&#10103;)<br><br><br>@color[yellow](&#10104;)<br><br><br>@color[yellow](&#10105;)<br><br><br>&#10106;</font></span></p>
@snapend


@snap[north-east span-92 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[white](Get the EDK II packages to a local workspace)
<br><br><br>&nbsp;@color[white](Select the Ref and correct Intel® FSP Package)
<br><br><br>&nbsp;@color[white](Copy a reference <font face="Consolas">OpenBoardPkg/BoardXXX</font> )
<br><br><br>&nbsp;@color[white](Use feature stages to port all required project  modules )
<br><br><br>&nbsp;
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>
@snapend

<!---  
5
-->

@snap[north-west span-10 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>@color[yellow](&#10102;)<br><br><br>@color[yellow](&#10103;)<br><br><br>@color[yellow](&#10104;)<br><br><br>@color[yellow](&#10105;)<br><br><br>@color[yellow](&#10106;)</font></span></p>
@snapend

@snap[north-east span-92 fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[white](Get the EDK II packages to a local workspace)
<br><br><br>&nbsp;@color[white](Select the Ref and correct Intel® FSP Package)
<br><br><br>&nbsp;@color[white](Copy a reference <font face="Consolas">OpenBoardPkg/BoardXXX</font> )
<br><br><br>&nbsp;@color[white](Use feature stages to port all required project  modules )
<br><br><br>&nbsp;@color[white](Validate each stage test points defined w/ each stage)
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>
@snapend



Note:
4 & 5 take the longest


Find a similar package or platform from the Open Board edk-platforms  that meets target project needs


1. Get the EDK II packages to a local workspace
2. Select the Ref and correct Intel® FSP Package
3. Copy a reference OpenBoardPkg/BoardXXX 
4. Use feature stages to port all required project  modules
5. Validate each stage test point results defined with each stage 



<!---  Section for Porting Task  -->

---?image=assets/images/binary-strings-black2.jpg
<!-- .slide: data-transition="none" -->
@title[Porting Task List Section]
<p align="center"><span style="font-size:01.25em"><font color="#e49436"><b>Porting Task List</b></span></p>

@snap[north-east span-95 ]
<br>
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%" ><span style="font-size:0.9em; font-weight: bold;" > <br><br> <br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

<!---  col of numbers Gray -->

@snap[north-west span-10 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>&#10102;<br><br><br>&#10103;<br><br><br>&#10104;<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend


@snap[north-west span-10 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>@color[yellow](&#10102;)<br><br><br>@color[yellow](&#10103;)<br><br><br>@color[yellow](&#10104;)<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend

@snap[north-east span-92 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[yellow](<b>Get the EDK II packages to a local workspace</b>)
<br><br><br>&nbsp;@color[yellow](<b>Select the Ref and correct Intel® FSP Package</b>)
<br><br><br>&nbsp;@color[yellow](<b>Copy a reference <font face="Consolas">OpenBoardPkg/BoardXXX</font></b> )
<br><br><br>&nbsp;@color[#808080](Use feature stages to port all required project  modules )
<br><br><br>&nbsp;@color[#808080](Validate each stage test points defined w/ each stage)
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>
@snapend



Note:
4 & 5 take the longest


Find a similar package or platform from the Open Board edk-platforms  that meets target project needs


1. Get the EDK II packages to a local workspace
2. Select the Ref and correct Intel® FSP Package
3. Copy a reference OpenBoardPkg/BoardXXX 
4. Use feature stages to port all required project  modules
5. Validate each stage test point results defined with each stage 


---?image=assets/images/slides/Slide6.JPG
@title[Analysis OpenBoard Reference Platforms]
<p align="right"><span class="gold" >@size[1.1](<b>Analysis OpenBoard Reference Platforms</b>)</span><span style="font-size:0.75em;" ></span></p>
@snap[north-west span-90 ]
<br>
<br>
<span style="font-size:0.8em;" ><br> Steps 1 - 3</span>
<br>
<br>
<ul style="list-style-type:disc; line-height:0.9;">
  <li class=fragment><span style="font-size:0.8em" >Find a similar OpenBoard EDK II Platform in Github <font face="Consolas">edk2_platforms</font> </span> </li>
  <li class=fragment><span style="font-size:0.8em" >Get the reference OpenBoard EDK II Platform from Github </span> </li>
  <li class=fragment><span style="font-size:0.8em" >Build the chosen reference OpenBoard EDK II Platform </span> </li>
  <li class=fragment><span style="font-size:0.8em" >Study the Build directory of the reference OpenBoard </span> </li>
  <li class=fragment><span style="font-size:0.8em" >Study the reference OpenBoard .FDF and DSC files </span> </li>
  <li class=fragment><span style="font-size:0.8em" >Copy a reference <font face="Consolas">OpenBoardPkg/BoardXXX</font>  to a new name (@size[.8em](i.e <font face="Consolas">NewOpenBoardPkg/NewBoardX</font> where string "@color[#A8ff60](<font face="Consolas">New</font>)" is meaningful to the project.)) </span> </li>
</ul>
@snapend


Note:
https://classroomaid.files.wordpress.com/2012/05/case-study.jpg

This is for steps 1 - 3

---
@title[Get the Reference OpenBoard Source ]
<p align="right"><span class="gold" >@size[1.1](<b>Get the Reference OpenBoard Source</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;">
Follow the Build and Download instructions for building the reference open board<br><br>
Download below repository to this WORKSPACE:
</span></p>
@snapend

@snap[north-east span-98 ]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
<font face="Arial">edk2 repository and Openssl</font><br>
git clone –recursive https://github.com/tianocore/edk2.git<br>
<br>
<font face="Arial">edk2-platforms repository</font><br>
git clone https://github.com/tianocore/edk2-platforms.git<br>
<br>
<font face="Arial">edk2-non-osi repository</font><br>
git clone https://github.com/tianocore/edk2-non-osi.git -b devel-MinPlatform<br>
<br>
<font face="Arial">FSP repository</font><br>
git clone https://github.com/IntelFsp/FSP.git<br>
</span></p>
@snapend

Note:

Get the source from the open source repositories to a local workspace directory


---
@title[Build the Reference OpenBoard ]
<p align="right"><span class="gold" >@size[1.1](<b>Build the Reference OpenBoard </b>)</span><span style="font-size:0.75em;" ></span></p>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;">
Open a Command Window and CD to the workspace directory<br><br>
For Linux  - CD  to the edk2 to run the "<font face="Consolas">edksetup.sh</font>" script
</span></p>

```
     $> cd edk2
     $> source edksetup.sh
     $> cd ../
```
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;">
CD  to the Intel directory in edk2-platforms 
</span></p>

```
	$> cd edk2-platforms/Platform/Intel

```

<p style="line-height:70%" align="left" ><span style="font-size:0.8em;">
Run the python build script with the OpenBoard Name (Kabylake is used)
</span></p>

```
    $> python build_bios.py –p KabyLakeRvp3

```


Note:

---
@title[Use the "Build" Directory as a Reference ]
<p align="right"><span class="gold" >@size[1.1](<b>Use the "Build" Directory as a Reference</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;">
After the Build is completed the Build directory will be a mirror of all the sources used to build the reference OpenBoard.<br><br>
This can serve as a cross reference to determine what sources are used in the chosen reference OpenBoard.
</span></p>
@snapend

@snap[north-east span-98 ]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
&lt;workspace&gt;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Build /KabylakeOpenBoardPkg /KabylakeRvp3 /DEBUG_&lt;BuildTag&gt; /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    FV /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    IA32 /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      &lt;Dirs built for SEC and PEI&gt; /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    X64 /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  &lt;Dirs built for DXE – BDS – Boot&gt; / <br>&nbsp;&nbsp;
</span></p>
@snapend

Note:

---
@title[Study the OpenBoard .DSC and .FDF ]
<p align="right"><span class="gold" >@size[1.1](<b>Study the OpenBoard .DSC and .FDF</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:85%" align="left" ><span style="font-size:0.9em;">
Porting requires becoming familiar with the chosen reference platforms DSC and FDF files. 
</span></p>
@snapend

@snap[north-west span-45 fragment ]
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-royal text-white waved my-box-pad2 ](<p style="line-height:70%" align="center"><span style="font-size:0.75em;" >@size[1.3em](DSC)<br><br>DSC will point to the correct Libraries used in the reference platform<br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-45 fragment ]
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-royal text-white waved my-box-pad2  ](<p style="line-height:70%" align="center"><span style="font-size:0.75em;" >@size[1.3em](FDF)<br><br>FDF will describe the Flash layout and FVs used for the different stages of the boot<br> flow<br>&nbsp;</span></p>)
@snapend

Note:
To do the porting of the OpenBoard platform requires becoming familiar with the ref openboard platform’s .DSC and FDF files.

FDF will describe the Flash layout and FVs used for the different stages of the boot flow

DSC will point to the correct Libraries used in the reference platform

---
@title[DSC Files for KabyLakeRvp3 ]
<p align="right"><span class="gold" >@size[1.1](<b>DSC Files for KabyLakeRvp3</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
/edk2-platforms/Platform/ <br>&nbsp;&nbsp;
  Intel/KabylakeOpenBoardPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
   KabylakeRvp3/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     @color[yellow](OpenBoardPkg.dsc)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkgConfig.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkgPcd.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkgBuildOption.dsc <br><br>
/edk2-platforms/Platform/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Intel/MinPlatformPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    Include/Dsc/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      CoreCommonLib.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      CorePeiLib.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      CoreDxeLib.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      CorePeiInclude.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      CoreDxeInclude.dsc<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[north-east span-45 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
/edk2-platforms/Silicon/ <br>&nbsp;&nbsp;
  Intel/KabylakeSiliconPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiPkgCommonLib.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiPkgPeiLib.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiPkgDxeLib.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiPkgPei.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiPkgDxe.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiPkgBuildOption.dsc
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[south-east span-45 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; "><br>
<font face="Consolas">@color[yellow](OpenBoardPkg.dsc)</font> – Includes all of the platform, common core,  and silicon related .dsc files
</span></p>
<br>
<br>
@snapend

Note:


By searching the top level include from /edk2-platforms/Platform \ 
<pre>
  Intel/KabylakeOpenBoardPkg \
   KabylakeRvp3
    OpenBoardPkg.dsc
</pre>

We see that it will INCLUDE the other core and silicon .dsc files.  Note the order is important with studying the .DSC files making note of the Sections that the files get included into. 



---
@title[Example: DSC File]
<p align="right"><span class="gold" >@size[1.1](<b>Example: DSC File</b>)</span><span style="font-size:0.8em;" ></span></p>

```
[Defines]
  #
  # Set platform specific package/folder name, same as passed from PREBUILD script.
  # PLATFORM_PACKAGE would be the same as PLATFORM_NAME as well as package build folder
  # DEFINE only takes effect at R9 DSC and FDF.
  #
  DEFINE      PLATFORM_PACKAGE                = MinPlatformPkg
  DEFINE      PLATFORM_SI_PACKAGE             = KabylakeSiliconPkg
  DEFINE      PLATFORM_SI_BIN_PACKAGE         = KabylakeSiliconBinPkg
  DEFINE      PLATFORM_FSP_BIN_PACKAGE        = AmberLakeFspBinPkg
  DEFINE      PLATFORM_BOARD_PACKAGE          = KabylakeOpenBoardPkg
  DEFINE      BOARD                           = KabylakeRvp3
  DEFINE      PROJECT                         = $(PLATFORM_BOARD_PACKAGE)/$(BOARD)

  #
  # Platform On/Off features are defined here
  #
  !include OpenBoardPkgConfig.dsc
  !include OpenBoardPkgPcd.dsc

[Defines]
!if gIntelFsp2WrapperTokenSpaceGuid.PcdFspModeSelection == 1
  #
  # For backward compatibility API mode will use KabylakeFspBinPkg.
  # KabylakeFspBinPkg only supports API mode.
  #
  DEFINE      PLATFORM_FSP_BIN_PACKAGE        = KabylakeFspBinPkg
!else
  #
  # AmberLakeFspBinPkg supports both API and Dispatch modes
  #
  DEFINE      PLATFORM_FSP_BIN_PACKAGE        = AmberLakeFspBinPkg
!endif

################################################################################
#
# Defines Section - statements that will be processed to create a Makefile.
#
################################################################################
[Defines]
  PLATFORM_NAME                       = $(PLATFORM_PACKAGE)
  PLATFORM_GUID                       = 465B0A0B-7AC1-443b-8F67-7B8DEC145F90
  PLATFORM_VERSION                    = 0.1
  DSC_SPECIFICATION                   = 0x00010005
  OUTPUT_DIRECTORY                    = Build/$(PROJECT)
  SUPPORTED_ARCHITECTURES             = IA32|X64
  BUILD_TARGETS                       = DEBUG|RELEASE
  SKUID_IDENTIFIER                    = ALL


  FLASH_DEFINITION                    = $(PROJECT)/OpenBoardPkg.fdf

  FIX_LOAD_TOP_MEMORY_ADDRESS         = 0x0
  DEFINE   TOP_MEMORY_ADDRESS         = 0x0

  #
  # Default value for OpenBoardPkg.fdf use
  #
  DEFINE BIOS_SIZE_OPTION = SIZE_70

################################################################################
#
# SKU Identification section - list of all SKU IDs supported by this
#                              Platform.
#
################################################################################
[SkuIds]
  0|DEFAULT              # The entry: 0|DEFAULT is reserved and always required.
  4|KabylakeRvp3
  0x60|KabyLakeYLpddr3Rvp3

################################################################################
#
# Library Class section - list of all Library Classes needed by this Platform.
#
################################################################################

!include $(PLATFORM_PACKAGE)/Include/Dsc/CoreCommonLib.dsc
!include $(PLATFORM_PACKAGE)/Include/Dsc/CorePeiLib.dsc
!include $(PLATFORM_PACKAGE)/Include/Dsc/CoreDxeLib.dsc
 . . ..


```


@snap[south-east span-45 ]
<p style="line-height:40% " align="right"><span style="font-size:0.55em;">
Link to <a href="https://github.com/tianocore/edk2-platforms/blob/master/Platform/Intel/KabylakeOpenBoardPkg/KabylakeRvp3/OpenBoardPkg.dsc"> Kabylake .DSC </a>
file
</span></p>
@snapend

Note:

Click on the link to view the whole .DSC file

---
@title[FDF Files for KabyLakeRvp3 ]
<p align="right"><span class="gold" >@size[1.1](<b>FDF Files for KabyLakeRvp3</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-47 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-52 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
/edk2-platforms/Platform/  <br>&nbsp;&nbsp;
  Intel/KabylakeOpenBoardPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
   Include/Fdf/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      FlashMapInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
   KabylakeRvp3<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    @color[yellow](OpenBoardPkg.fdf)<br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[north-east span-50 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
/edk2-platforms/Platform/ <br>&nbsp;&nbsp;
  Intel/MinPlatformPkg/<br>&nbsp;&nbsp;
  Include/Fdf/<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CorePreMemoryInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CorePostMemoryInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CoreUefiBootInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CoreOsBootInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CoreSecurityPreMemoryInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CoreSecurityPostMemoryInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     CoreSecurityLateInclude.fdf<br>&nbsp;&nbsp;&nbsp;&nbsp;
     RuleInclude.fdf<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[south-west span-47 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; "><br>
<font face="Consolas">@color[yellow](OpenBoardPkg.fdf)</font> – Includes all of the platform and common core related .fdf files
</span></p>
<br>
<br>
@snapend

Note:

Similar to the .DSC, by searching the top level include from /edk2-platforms/Platform \ 
<pre>
  Intel/KabylakeOpenBoardPkg \
   KabylakeRvp3
    OpenBoardPkg.fdf
</pre>

We see that it will INCLUDE the other common core  files.  also Note, 
the order is important with studying the .FDF files making note of the Sections that the files get included into. 

This determines where in the flash map FV and Modules will be placed..

---?image=assets/images/slides/Slide14.JPG
@title[Flash Layout for Kabylake ]
<p align="right"><span class="gold" >@size[1.1](<b>Flash Layout for Kabylake</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
edk2-platforms/Platform/ <br>&nbsp;&nbsp;
  Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;
   KabylakeOpenBoardPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    Include/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Fdf/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      @color[yellow](FlashMapInclude.fdf)
<br>&nbsp;&nbsp;
</span></p>
@snapend


Note:

The mapping closely corresponds to the different FV that get created as part of the build process


---
@title[Example: Kabylake  .FDF file ]
<p align="right"><span class="gold" >@size[1.1](<b>Example: Kabylake .FDF file</b>)</span><span style="font-size:0.8em;" ></span></p>

```
[FD.KabylakeRvp3]
 #
  . . .
[FV.FvPreMemory]
BlockSize          = $(FLASH_BLOCK_SIZE)
FvAlignment        = 16
  . . .
INF  UefiCpuPkg/SecCore/SecCore.inf
INF  MdeModulePkg/Core/Pei/PeiMain.inf
!include $(PLATFORM_PACKAGE)/Include/Fdf/CorePreMemoryInclude.fdf

INF $(PLATFORM_PACKAGE)/PlatformInit/ReportFv/ReportFvPei.inf
INF $(PLATFORM_PACKAGE)/PlatformInit/PlatformInitPei/PlatformInitPreMem.inf
INF IntelFsp2WrapperPkg/FspmWrapperPeim/FspmWrapperPeim.inf
INF $(PLATFORM_PACKAGE)/PlatformInit/SiliconPolicyPei/SiliconPolicyPeiPreMem.inf

. . .

[FV.FvPostMemoryUncompact]
BlockSize          = $(FLASH_BLOCK_SIZE)
FvAlignment        = 16
ERASE_POLARITY     = 1
 . . .

!include $(PLATFORM_PACKAGE)/Include/Fdf/CorePostMemoryInclude.fdf

# Init Board Config PCD
INF $(PLATFORM_PACKAGE)/PlatformInit/PlatformInitPei/PlatformInitPostMem.inf
INF IntelFsp2WrapperPkg/FspsWrapperPeim/FspsWrapperPeim.inf
INF $(PLATFORM_PACKAGE)/PlatformInit/SiliconPolicyPei/SiliconPolicyPeiPostMem.inf

  . . .

[FV.FvUefiBootUncompact]
BlockSize          = $(FLASH_BLOCK_SIZE)
FvAlignment        = 16
 . . .

!include $(PLATFORM_PACKAGE)/Include/Fdf/CoreUefiBootInclude.fdf

INF  UefiCpuPkg/CpuDxe/CpuDxe.inf
INF  MdeModulePkg/Bus/Pci/PciHostBridgeDxe/PciHostBridgeDxe.inf

INF  MdeModulePkg/Bus/Pci/SataControllerDxe/SataControllerDxe.inf
INF  MdeModulePkg/Bus/Ata/AtaBusDxe/AtaBusDxe.inf
INF  MdeModulePkg/Bus/Ata/AtaAtapiPassThru/AtaAtapiPassThru.inf
INF  MdeModulePkg/Universal/Console/GraphicsOutputDxe/GraphicsOutputDxe.inf

INF  ShellPkg/Application/Shell/Shell.inf

INF  $(PLATFORM_PACKAGE)/PlatformInit/PlatformInitDxe/PlatformInitDxe.inf
INF  IntelFsp2WrapperPkg/FspWrapperNotifyDxe/FspWrapperNotifyDxe.inf

INF  $(PLATFORM_PACKAGE)/Test/TestPointStubDxe/TestPointStubDxe.inf



```


@snap[south-east span-45 ]
<p style="line-height:40% " align="right"><span style="font-size:0.55em;">
Link to <a href="https://github.com/tianocore/edk2-platforms/blob/master/Platform/Intel/KabylakeOpenBoardPkg/KabylakeRvp3/OpenBoardPkg.fdf"> Kabylake .FDF </a>
file
</span></p>
@snapend

Note:

Click on the link to view the whole .FDF file


---
@title[Copy a Similar Reference OpenBoard]
<p align="right"><span class="gold" >@size[1.1](<b>Copy a Similar Reference OpenBoard</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-50 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
MyWorkSpace/<br>&nbsp;&nbsp;
edk2/<br>&nbsp;&nbsp; &nbsp;&nbsp;
  - "@color[#FFC000](edk2 Common)"<br>&nbsp;&nbsp;
edk2-platforms/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Platform/ "@color[#FFC000](Platform)"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       MinPlatformPkg/ "@color[#FFC000](Board common)"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       KabylakeOpenBoardPkg<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       @color[yellow](NewOpenBoardPkg)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
           @color[yellow](BoardXxx)/ "@color[#FFC000](Board)"<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       KabyLakeSilconPkg/"@color[#FFC000](Silicon)"<br>&nbsp;&nbsp;
edk2-non-osi/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;
FSP/"Silicon"<br>&nbsp;&nbsp;&nbsp;&nbsp;
  KabyLakeFspBinPkg<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north span-5 ]
<br>
<br>
<br>
<ul style="list-style-type:none; line-height:0.7;">
  <li><span style="font-size:0.65em" >@color[gray]( 1. )<br><br></span> </li>
  <li><span style="font-size:0.65em" >@color[gray]( 2. )<br><br> </span> </li>
  <li><span style="font-size:0.65em" > 3. </span> </li>
</ul>
@snapend


@snap[north-east span-48 ]
<br>
<br>
<br>
<ul style="list-style-type:none; line-height:0.7;">
  <li><span style="font-size:0.65em" > @color[gray](Get the EDK II packages locally to the workspace)</span> </li>
  <li><span style="font-size:0.65em" > @color[gray](Select the Ref  OpenBoard and correct Intel® FSP silicon initialization solution)</span> </li>
  <li class=fragment><span style="font-size:0.65em" > Copy a reference - <font face="Consolas">GenerationOpenBoardPkg/BoardXxx</font> to a new directory  </span> </li>
</ul>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; "><br>
<font face="Consolas">@color[yellow](NewOpenBoardPkg) & @color[yellow](BoardXxx)</font>
</span></p>
<br>
<br>
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Only make changes in the "<font face="Consolas">@color[yellow](NewOpenBoardPkg)</font>"<br><br>&nbsp;</span></p>)
@snapend


Note:


The build process creates this directory - Build/

MyWorkSpace – directory from the “git” of repositories

Build –p .dsc from the BOARD Directory

The architecture is designed to support a maintainer ownership model. For example, board developers should not directly modify (fork) the platform, silicon, or common code. More details on conventional usage of the package classifications can be found in supplemental literature from UEFI Forum, TianoCore.org, and others.
  (see https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Development-Process)


---
@title[PI Modules – One board, one dir]
<p align="right"><span class="gold" >@size[1.1](<b>PI Modules – One board, one dir</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
@color[yellow](KabylakeOpenBoardPkg)<br>&nbsp;&nbsp;
  Acpi<br>&nbsp;&nbsp;
  FspWrapper<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiFspPolicyUpdateLib<br>&nbsp;&nbsp;
  Include<br>&nbsp;&nbsp;
  Library<br>&nbsp;&nbsp;
  @color[yellow](KabylakeRvp3)<br>&nbsp;&nbsp;
   . . .<br>&nbsp;&nbsp;
  @color[yellow](KabylakeRvp7 )<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Include<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library<br>&nbsp;&nbsp;&nbsp;&nbsp;
       . . .<br>&nbsp;&nbsp;&nbsp;&nbsp;
    OpenBoardPkg.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    OpenBoardPkg.fdf
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
@color[yellow](KabylakeRvp7 )<br>&nbsp;&nbsp;
  Library<br>&nbsp;&nbsp;&nbsp;&nbsp;
    BoardInitLib<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiBoardInitPreMemLib<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiBoardInitPostMemLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
<br>&nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  
    BasePlatformHookLib<br>&nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;

    BoardAcpiLib<br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[north-east span-78 fragment ]
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
 @fa[arrow-left fa-2x gp-bullet-yellow] 
<br>
 @fa[arrow-left fa-2x gp-bullet-yellow] 
</span></p>
@snapend



Note:

This example KabylakeRvp3 and KabylakeRvp7 are very similar but different enough to make a new directory for KabylakeRvp7

If we need to add a new board, such as Rvp7, we can copy the KabylakeRv3 folder to KabylakeRvp7 folder, and update all the modules in this KabylakeRvp7. 
Once we move the board specific code to the board specific directory, the generic board code should not contain any board specific code. For example, we do not put PeiFspPolicyUpdateLib 
into KabylakeRvp3, because this code only consumes a set of PCDs, such as PcdMrcRcompResistor, PcdSpecificLpHsioPtssTable1, PcdHdaVerbTable, etc. A KabylakeRvp3 board specific code BoardInitLib 
produces these PCDs and Kabylake common board code consumes these PCDs 



---
@title[New OpenBoard Directory]
<p align="right"><span class="gold" >@size[1.1](<b>New OpenBoard Directory</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
@color[yellow](NwqOpenBoardPkg)<br>&nbsp;&nbsp;
  Acpi<br>&nbsp;&nbsp;
  FspWrapper<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiFspPolicyUpdateLib<br>&nbsp;&nbsp;
  Include<br>&nbsp;&nbsp;
  Library<br>&nbsp;&nbsp;
   @color[yellow](BoardXxx )<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Include<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library<br>&nbsp;&nbsp;&nbsp;&nbsp;
       . . .<br>&nbsp;&nbsp;&nbsp;&nbsp;
    OpenBoardPkg.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;
    OpenBoardPkg.fdf
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
@color[yellow](BoardXxx )<br>&nbsp;&nbsp;
  Library<br>&nbsp;&nbsp;&nbsp;&nbsp;
    BoardInitLib<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiBoardInitPreMemLib<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiBoardInitPostMemLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
<br>&nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  
    BasePlatformHookLib<br>&nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;

    BoardAcpiLib<br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend



Note:

This example we are coping the KabylakeOpenBoardPkg to the NewOpenBoardPkg since the board had many differences

Example the flash layout is too different to use the same platform common board.

Also rename the board to a meaningful name, this case “BoardXxx”



<!---  Section for Porting Task  -->

---?image=assets/images/binary-strings-black2.jpg
<!-- .slide: data-transition="none" -->
@title[Porting Task List Section]
<p align="center"><span style="font-size:01.25em"><font color="#e49436"><b>Porting Task List</b></span></p>

@snap[north-east span-95 ]
<br>
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%" ><span style="font-size:0.9em; font-weight: bold;" > <br><br> <br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

<!---  col of numbers Gray -->

@snap[north-west span-10 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>&#10102;<br><br><br>&#10103;<br><br><br>&#10104;<br><br><br>&#10105;<br><br><br>&#10106;</font></span></p>
@snapend


@snap[north-west span-10 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:01.0em" ><font color="#808080"><br><br>&#10102;<br><br><br>&#10103;<br><br><br>&#10104;<br><br><br>@color[yellow](&#10105;)<br><br><br>@color[yellow](&#10106;)</font></span></p>
@snapend


@snap[north-east span-92 ]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.85em" >
<br>&nbsp;        @color[#808080](Get the EDK II packages to a local workspace)
<br><br><br>&nbsp;@color[#808080](Select the Ref and correct Intel® FSP Package)
<br><br><br>&nbsp;@color[#808080](Copy a reference <font face="Consolas">OpenBoardPkg/BoardXXX</font>)
<br><br><br>&nbsp;@color[yellow](<b>Use feature stages to port all required project  modules</b> )
<br><br><br>&nbsp;@color[yellow](<b>Validate each stage test points defined w/ each stage</b>)
<br><br>&nbsp;<br><br>&nbsp;  </font></span></p>
@snapend



Note:
4 & 5 take the longest


Find a similar package or platform from the Open Board edk-platforms  that meets target project needs


1. Get the EDK II packages to a local workspace
2. Select the Ref and correct Intel® FSP Package
3. Copy a reference OpenBoardPkg/BoardXXX 
4. Use feature stages to port all required project  modules
5. Validate each stage test point results defined with each stage 

---?image=assets/images/binary-strings-black2.jpg
@title[Port by Stages Section 1]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Port by Stages</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Use the staged architecture as a porting guide</span>


---?image=assets/images/slides/Slide_TableDHote.JPG
@title[Staged Approach by Features Section]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>
@snap[north-west span-70 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >PCD Variable:<br></span>
<span style="font-size:0.5em; font-family:Consolas;">
gPlatformModuleTokenSpaceGuid.PcdBootStage
</span></p>
@snapend

@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 1&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Enable Debug &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 2&nbsp;</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Memory Initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 3&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Boot to UEFI Shell only &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 4&nbsp;</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Boot ot OS</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 5&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Boot ot OS w/ Security enabled&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 6&nbsp;</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Advanced Feature Selection</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 7&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Performance Opetimizations &nbsp;</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  Pronounced "Tab la dout"
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables. Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations

Within the DSC and  FDF choose which modules to include based on PCD
Example
<pre>
DSC:
[PcdsFeatureFlag]
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterMemInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdUefiSecureBootEnable|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdTpm2Enable|FALSE

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 1
 gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|TRUE
!endif

Example FDF
!if gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly == FALSE
INF  MdeModulePkg/Universal/FaultTolerantWriteDxe/FaultTolerantWriteSmm.inf
INF  MdeModulePkg/Universal/Variable/RuntimeDxe/VariableSmmRuntimeDxe.inf
INF  MdeModulePkg/Universal/Variable/RuntimeDxe/VariableSmm.inf
!endif
</pre>



---?image=assets/images/slides/Slide_TableDHote.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Staged Approach by Features Section ]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>


@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Stage 1&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Enable Debug &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 2&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Memory Initialization)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 3&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot to UEFI Shell only &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 4&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 5&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS w/ Security enabled&nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 6&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Advanced Feature Selection)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 7&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Performance Opetimizations &nbsp;)</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations


---?image=assets/images/slides/Slide23.JPG
@title[Boot Flow – Stage 1]
<p align="right"><span class="gold" >@size[1.1](<b>Boot Flow – Stage 1</b>)</span><span style="font-size:0.75em;" ></span></p>


Note:

Stage I is contained within SEC and PEI phases. Code must not be compressed and content must be capable of being mapped to memory by hardware or other firmware.



---?image=assets/images/slides/Slide24.JPG
@title[High Level Control Flow – Stage 1]
<p align="right"><span class="gold" >@size[1.1](<b>High Level Control Flow – Stage 1</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-50 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.85em; "><br>
Major Execution Activities
</span></p>

<ul style="list-style-type:disc; line-height:0.8;">
  <li><span style="font-size:0.8em" > Establish temporary memory (initialize MTRR)</span> </li>
  <li><span style="font-size:0.8em" > Perform pre-memory board-specific initialization</span> </li>
  <li><span style="font-size:0.8em" > Board detection</span> </li>
  <li><span style="font-size:0.8em" > GPIOs</span> </li>
  <li><span style="font-size:0.8em" > Serial Port initialization (Example: SIO, HSUART)</span> </li>
</ul>
@snapend

Note:

The objective of Stage I is to provide a foundation for more complex development in later stages. The board should implement a board-specific minimal code path capable of firmware debug output. Basic debug capability serves as a base for development activities in later stages. As Stage I is inherently foundational to product execution it may include more content and complexity than the functionality strictly required for debug output.


These activities, contained within SEC and PEI phases, do not map 1:1 to the required functions. Some of this flow is already well defined by UEFI or EDK II specifications. 


---?image=assets/images/slides/Slide25.JPG
@title[Location of Stage 1 Modules]
<p align="right"><span class="gold" >@size[1.1](<b> Location of Stage 1 Modules</b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Check the Board/Platform .FDF file layout<br><br>&nbsp;</span></p>)
@snapend


Note:

Where’s the platform code start? or the first point where the platform code is executed


As the foundational stage for further functionality, Stage I may include additional content beyond what is strictly required to meet the stage objective. Typically this will include silicon initialization code that may be packaged in a variety of mechanisms including varying size binary blobs. 

The Stage I modules will be combined into FVs to make up the Stage I components

---
@title[Stage 1 Firmware Volumes]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 1 Firmware Volumes</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Name&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Content</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvPreMemory&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >SEC + StatusCode&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvBspPreMemory&nbsp;</span></p></td>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Pre-memory board initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspT&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >SEC silicon initialization - T-RAM &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspM&nbsp;</span></p></td>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Memory initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;-&gt;FvPreMemorySilicon&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Pre-memory silicon initialization&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspS&nbsp;</span></p></td>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Silicon initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;-&gt;FvPostMemorySilicon&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".0%2"><p style="line-height:01%"><span style="font-size:0.5em" >Post-memory silicon initialization &nbsp;</span></p></td>
	</tr>
</table>
<br>
@snapend



Note:


Use the Platform .Fdf File to determine which modules map to each FV
Typically this will include silicon initialization code that may be packaged in a variety of mechanisms including varying size binary blobs. In the layout shown in this slide, the Intel® FSP solution is shown as an example. In this case, the FSP binary can be rebased and integrated in one step rather than distributing the work for the FSP-M and FSP-S rebase unnecessarily across later stages. 
A Note that a child FV is a FV embedded within the parent FV. The child FV is identified by a file type of EFI_FV_FILETYPE_FIRMWARE_VOLUME_IMAGE.



| `Name`              | `Content`                          | `Compressed` | `Parent FV` |
| ------------------- | ---------------------------------- | ------------ | ----------- |
| FvPreMemory         | SEC + StatusCode                   | No           | None        |
| FvBspPreMemory      | Pre-memory board initialization    | No           | None        |
| FvFspT              | SEC silicon initialization         | No           | None        |
| FvFspM              | Memory initialization              | No           | None        |
| FvPreMemorySilicon  | Pre-memory silicon initialization  | No           | FvFspM      |
| FvFspS              | Silicon initialization             | No           | None        |
| FvPostMemorySilicon | Post-memory silicon initialization | Yes          | FvFspS      |




---
@title[Stage 1 FVs Contents]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 1 FVs Contents</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>FV&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Components</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Purpose</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvPreMemory&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >@color[yellow](SecCore.efi)&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".020%" width="70%"><p style="line-height:022%"><span style="font-size:0.45em" >
			&bull; &nbsp;Reset Vector<br>
			&bull; &nbsp;Passes PEI core the address of FvFspM<br>
			&bull; &nbsp;Passes PEI core the debug configuration
		&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >ReportFvPei.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >Installs firmware volumes</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >PlatformInitPreMemory.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >Performs pre memory initialization&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >SiliconPolicyPeiPreMemory.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >Publishes silicon initialization configuration&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspT&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >TempRamInit API &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >Set up Temp Memory (CAR)&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspM&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >FspmWrapperPeim.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >call FspMemoryInit API&nbsp;</span></p></td>
	</tr>
</table>
<br>
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Mapped according to .FDF file layout<br><br>&nbsp;</span></p>)
@snapend


Note:


Use the Platform .Fdf File to determine which modules map to each FV


https://github.com/tianocore-docs/edk2-MinimumPlatformSpecification/blob/master/3_stage_1_minimum_debug/32_firmware_volumes.md#32-firmware-volumes


As the foundational stage for further functionality, Stage I may include additional content beyond what is strictly required to meet the stage objective. Typically this will include silicon initialization code that may be packaged in a variety of mechanisms including varying size binary blobs. In the layout shown in this slide, the Intel® FSP solution is shown as an example. In this case, the FSP binary can be rebased and integrated in one step rather than distributing the work for the FSP-M and FSP-S rebase unnecessarily across later stages. Note that a child FV is a FV embedded within the parent FV. The child FV is identified by a file type of EFI_FV_FILETYPE_FIRMWARE_VOLUME_IMAGE.
| `Binary` | `FV`              | `Components`                  | `Purpose`                                                                                                                      |
| -------- | ----------------- | ----------------------------- | --------------------------------------------------------------------------------------- |
| Stage I  | FvPreMemory.fv    | SecCore.efi                   |  Reset Vector - Passes PEI core the address of FvFspM - Passes PEI core the debug configuration   |
|          |                   | ReportFvPei.efi               |  Installs firmware volumes                                                                                     |
|          |                   | SiliconPolicyPeiPreMemory.efi |  Publishes silicon initialization configuration                                                                |
|          |                   | PlatformInitPreMemory.efi     |  Performs pre memory initialization                                                                            |
|          |                   | Additional Components         |  Additional pre-memory components required for Stage I boot                                                    |
|          | FvBspPreMemory.fv | Additional Components         |  Advanced pre-memory board support components                                                                  |
|          | FvFspT.fv         | PlatformSec.efi               |  Initializes T-RAM silicon functionality                                                                       |
|          |                   |                               |  Tests T-RAM functionality                                                                                     |
|          |                   | Additional Components         |                                                                                                                                |
|          | FvFspM.fv         | PeiCore.efi                   |  PEI services and dispatcher                                                                                   |
|          |                   | PcdPeim.efi                   |  PCD service                                                                                                   |
|          |                   | FspPlatform.efi               |  Converts UPD to Policy PPI                                                                                    |
|          |                   | FvPreMemorySilicon.fv         |                                                                                                                                |
|          |                   | (child FV)                    |                                                                                                                                |
|          |                   | Additional Components         |  Pre-memory silicon initialization components                                                                  |
|          |                   | ReportStatusCodeRouterPei.efi |  Provide status code infrastructure                                                                            |
|          |                   | StatusCodeHandlerPei.efi      |  Provide status code listeners                                                                                 |
|          |                   | Additional Components         |                                                                                                                                |
|          | FvFspS.fv         | FvPostMemorySilicon.fv        |                                                                                                                                |
|          |                   | (child FV)                    |                                                                                                                                |
|          |                   | Additional Components         |  Post-memory silicon initialization components                                                                 |
|          |                   | Additional components         |                                                                                                                                |



---
@title[Stage 1 Modules]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 1 Modules</b>)</span><span style="font-size:0.75em;" ><br> - Example <font face="Consolas">SecCore.efi</font></span></p>


@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%"><span style="font-size:0.8em; font-family:Consolas;" ><br> 
<font face="Arial">Producing Package -  </font>UefiCpuPkg<br><br>
<font face="Arial">Libraries Consumed -  </font>PlatformSecLib, SerialPortLib
<br></span></p>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Library</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:50%"><span style="font-size:0.65em" ><b>API Definition</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:50%"><span style="font-size:0.65em" ><b>Producing Pkg</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Description</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > PlatformSecLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > UefiCpuPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:010%"><span style="font-size:0.45em" >Reset vector and SEC initialization code.  </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SerialPortLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MdeModulePkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > Board&lt;X&gt;Pkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:030%"><span style="font-size:0.45em" > SIO vendor specific initialization to enable serial port. </span></p></td>
	</tr>
</table>
<br>
@snapend




Note:


Only modules found in the BoardPkg should be modified for board porting. MinPlatformPkg and other common package contents must not be directly modified. BoardPkg and SiliconPkg modules will have multiple instances to support different boards and different silicon.


Board porting will require creation of libraries identified as produced by the BoardPkg. Depending on the board, there may be existing libraries that are sufficient for a board, so it is important to assess the utility of existing library instances when developing board support.



---
@title[Stage 1 Platform Libraries]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 1 Platform Libraries</b>)</span><span style="font-size:0.75em;" ></b></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable-1">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Item</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>API Definition</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Producing Pkg</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Description</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardInitLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:01%"><span style="font-size:0.4em" > Board initialization library. </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > ReportFvLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:020%"><span style="font-size:0.4em" > Installs platform firmware volumes. </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SerialPortLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MdeModulePkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:030%"><span style="font-size:0.4em" >  SIO vendor specific initialization to enable serial port.</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPolicyInitLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > IntelSiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:030%"><span style="font-size:0.4em" > Provides default silicon configuration policy data. </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPolicyUpdateLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > IntelSiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:030%"><span style="font-size:0.4em" > Provides board updates to silicon configuration policy data. </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > PlatformSecLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > UefiCpuPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em" >  Reset vector and SEC initialization code.</span></p></td>
	</tr>
</table>
<br>
@snapend




Note:

https://github.com/tianocore-docs/edk2-MinimumPlatformSpecification/blob/master/3_stage_1_minimum_debug/33_modules.md#332-platform-architecture-libraries

To find the Libraries for the Platform specific code
1 Search the Work space .DSC files for the string of the library
2 Open the .DSC files associated with the platform
3 Determine which Library is used and that should have the build path in the workspace.

Board porting will require creation / porting of libraries identified as produced by the BoardPkg. Depending on the board, there may be existing libraries that are sufficient for a board, so it is important to assess the utility of existing library instances when developing board support.


---?image=assets/images/slides/Slide30.JPG
@title[How to search for Libraries in the Workspace]
<p align="right"><span class="gold" >@size[1.1](<b>How to search for Libraries in the Workspace</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-67 ]
<br>
<br>
<br>
<br>
<ul style="list-style-type:none; line-height:0.7;">
  <li><span style="font-size:0.7em" >1. Search the workspace .DSC files for the <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;string of the library<br></span> </li><br>
  <li><span style="font-size:0.7em" >2. Open the .DSC files associated with the <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;open board platform project<br></span> </li><br>
  <li><span style="font-size:0.7em" >3. Determine which Library is used and that <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;should have the build path in the workspace<br></span> </li><br>
  <li><span style="font-size:0.7em" >4. DSC file will have similar to:</span> </li>
  <li><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;&nbsp;&nbsp;@color[yellow](SomeLib)|Path_to_the_Library_used.inf</span> </li>
</ul>

@snapend



Note:
http://sustituciondepuestosclaves.wikispaces.com/Metodo+de+Sustitucion+de+Puestos+Claves 

Another Note: use Regular expressions to find multiple strings:
Example, to fine the strings “Hob” and “Serial”

    Serial.*Hob|Hob.*Serial  

reg exp to find string1 "Serial" string2 "Hob"



---?image=assets/images/slides/Slide31.JPG
@title[Platform SEC Lib - Kabylake ]
<p align="right"><span class="gold" >@size[1.1](<b>Platform SEC Lib - Kabylake </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[south-west span-49 ]
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[south-east span-49 ]
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;">
Search the board platform .DSC file for where the @color[#A8ff60](<font face="Consolas">PlatformSecLib</font>) is in the Platform-Board Tree
</span></p>
<p style="line-height:50%" align="left" ><span style="font-size:0.7em;">
DSC FILE:<br>
<font face="Consolas">
@size[.7em](@color[#A8ff60](PlatformSecLib)|MinPlatformPkg/FspWrapper/Library/\ )<br>&nbsp;&nbsp;
  @size[.7em](SecFspWrapperPlatformSecLib/@color[yellow](SecFspWrapperPlatformSecLib.inf))
</font>
<br>
<br>
@size[.8em](Directory:)
</span></p>
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br><br>
Library/SecFspWrapperPlatformSecLib/<br>&nbsp;&nbsp;
    FsptCoreUpd.c<br>&nbsp;&nbsp;
    FspWrapperPlatformSecLib.c<br>&nbsp;&nbsp;
    Platforminint.c<br>&nbsp;&nbsp;
    @color[yellow](SecFspWrapperPlatformSecLib.inf)<br>&nbsp;&nbsp;
    SecGetPerformance.c<br>&nbsp;&nbsp;
    SecPlatforminformation.c<br>&nbsp;&nbsp;
    SecRamInitData.c<br>&nbsp;&nbsp;
    SecTemRamDone.c<br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[north-east span-45 ]
<br>
<br>
<br>
<br>
<br>
<br><p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br><br><br><br>
IA32/<br>&nbsp;&nbsp;
   fsp.h<br>&nbsp;&nbsp;
   PeiCoreEntry.nasm<br>&nbsp;&nbsp;
   @color[#A8ff60](SecEntry.nasm)<br>&nbsp;&nbsp;
   Stack.nasm<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend



@snap[north-east span-28 fragment ]
<br>
<br>
<br>
<br>
<br>
<br><p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br><br><br><br>
<br>&nbsp;&nbsp;
   <br>&nbsp;&nbsp;
   <br>&nbsp;&nbsp;
   &nbsp;&nbsp;@fa[arrow-left fa-2x gp-bullet-yellow]<i>@size[.7em](&nbsp;&nbsp;_ModuleEntryPoint)</i><br>&nbsp;&nbsp;
   <br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend



Note:

Since we now know that the SEC code is in the FV –FvPreMemory and the module is SecCore.efi and the Libraries for SecCore.efi are PlatformSecLib and SerialPortLib we can search the board platform .DSC file for where the PlatformSecLib is in the Platform-Board Tree

The ModuleEntryPoint is in SecEntry.nasm

Entry point after reset vector is platform specific
SecEntry.asm
ModuleEntryPoint

http://4.bp.blogspot.com/-_yn2oKMT4i4/UUdVkp1rBuI/AAAAAAAAAlw/lGtpuQsmqOk/s1600/icon_detective.png

Of this slide we have what we need to port our new package platform for the SEC  phase.
We find this code in our new platform package directory under the library directory under the directory called something like new platform SEC lib. Under this directory we see that we have a “C”, “H” and Inf files, And we also see another directory, in our case for our example platform, we have an IA32 directory. This directory would have assembly language source files for our port.

Let’s take a look at the details of these files:
After the reset vector and after those initial architecture specific instructions, a jump will be made into the platform SEC library code. The Entry point after common reset vector is platform specific in SecEntry.nasm  with the label _ModuleEntryPoint.

The file SecEntry.nasm – calls the entry for setting up our temporary memory and the Application Processors
We will need to look at the code at the label SecEntry.nasm where we would  make a call to set up our temporary memory and the cache as RAM. 

From reset vector to _ModuleEntryPoint
;   Transition to non-paged flat-model protected mode from a
;   hard-coded GDT that provides exactly two descriptors.
;   This is a bare bones transition to protected mode only
;   used for a while in PEI and possibly DXE.
;
;   After enabling protected mode, a far jump is executed to
;   transfer to PEI using the newly loaded GDT.

---?image=assets/images/slides/Slide32.JPG
@title[Establish Temporary Memory ]
<p align="right"><span class="gold" >@size[1.1](<b>Establish Temporary Memory </b>)</span><span style="font-size:0.75em;" ><br>Call to FSP API </span></p>


@snap[north-west span-60 ]
<br>
<br>
<p style="line-height:80%" align="left" ><span style="font-size:0.8em;">
Call to TempRamInit API  located in the FSP Binary module
</span></p>
@snapend


@snap[west span-40 fragment]
@box[bg-green-pp text-black waved my-box-pad2 ](<p style="line-height:70%" align="center"><span style="font-size:0.65em; font-family:Consolas;" >@size[1.3em](FSP-T)<br><br>TempRamInit API<br><br>&nbsp;</span></p>)
@snapend



@snap[south-west span-60 fragment]
<p style="line-height:70%" align="left"><span style="font-size:0.55em; font-family:Consolas;" >
TempRamInit Api 
</span></p>
<ul style="list-style-type:disc; line-height:0.6;">
  <li><span style="font-size:0.55em" >Initializes T-RAM silicon functionality<br>@size[.7em]( &nbsp;&nbsp;&nbsp;&nbsp;- No Evection mode / Cache As Ram)</span> </li>
  <li><span style="font-size:0.55em" >Tests T-RAM functionality</span> </li><br>
</ul>
<br>
<br>
@snapend


Note:

The Temp memory is set up through the FSP TempRamInit API

Call to the TempRamInit API is made that is located in the FSP Binary module
The  FSP binary is rebased for the FvFspT Firmware Volume.

Boot Loader must pass valid CAR region for FSP stack use through FSPM_UPD.FspmArchUpd.StackBase and
FSPM_UPD.FspmArchUpd.StackSize UPDs.
The minimum FSP stack size required for this revision of FSP is 160KB, stack base is 0xFEF17F00 by default. (from KabyLake FSP integraton Guide (KBLK IG)

At the end of TempRamExit the original code and data caching are disabled. FSP will reconfigure all MTRRs as
described in the table below for performance optimization.
Memory range Cache Attribute
0x00000000 - 0x0009FFFF Write back
0x000C0000 - Top of Low Memory Write back
0xFF800000 - 0xFFFFFFFF (Flash region) Write protect
0x1000000000 - Top of High Memory Write back
If the boot loader wish to reconfigure the MTRRs differently, it can be overridden immediately after this API call.


---
@title[Transition to PEI Entry Point ]
<p align="right"><span class="gold" >@size[1.1](<b>Transition to PEI Entry Point </b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:80%" align="left" ><span style="font-size:0.75em;">
SecMain calls the entry point into PEI Core
</span></p>

```
Secmain(  
{ . . .
  // Transfer the control to the PEI core
  ASSERT (PeiCoreEntryPoint != NULL);
  (*PeiCoreEntryPoint) (SecCoreData, PpiList); 
  UNREACHABLE ();

```

<p style="line-height:70%" align="left" ><span style="font-size:0.75em;">
<font face="Consolas">@size[.8em](PeiCore)</font> is the <font face="Consolas">@size[.8em](PeiCoreEntryPoint)</font> in the <font face="Consolas">@size[.8em](FvPreMemory)</font>  Firmware Volume:<Br>
 <font face="Consolas">@size[.7em](@color[yellow](edk2/MdeModulePkg/Core/Pei/PeiMain PeiMain.c))</font>
</span></p>

```
EFIAPI
PeiCore (
  IN CONST EFI_SEC_PEI_HAND_OFF        *SecCoreDataPtr,
  IN CONST EFI_PEI_PPI_DESCRIPTOR      *PpiList,
  IN VOID                              *Data
  )
{


```

Note:

Same ase slide


---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules - Stage 1 ]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules <br>- Stage 1</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
MinPlatformPkg/<br>&nbsp;&nbsp;
  Include/<br>&nbsp;&nbsp;&nbsp;&nbsp;
     Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	   @color[yellow](BoardnitLib.h)<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;
  . . .<br>&nbsp;&nbsp;
  @color[cyan](PlatformInit/)<br>&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  PlatformInitPreMem/<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-46 ]
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
BoardDetect&lpar;&rpar;<br>
BoardDebugInit&lpar;&rpar;<br>
BoardBootModeDetect&lpar;&rpar;<br>
BoardInitBeforeMemoryInit&lpar;&rpar;<br>
<br>&nbsp;&nbsp;
</span></p>
@snapend




@snap[north-east span-72 fragment]
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
<br>
<br>
<br>
<font face="Arial">@size[1.7](@color[#A8ff60]( <b>&larr;</b>)) &nbsp;&nbsp;// hooks</font><br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-46 ]
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
BoardDetect&lpar;&rpar;<br>
BoardDebugInit&lpar;&rpar;<br>
BoardBootModeDetect&lpar;&rpar;<br>
BoardInitBeforeMemoryInit&lpar;&rpar;<br>
<br>&nbsp;&nbsp;
</span></p>
@snapend




@snap[south span-95 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em">PlatformInit folder <font face="Consolas">@size[.8em](PlatformInit)</font> controls<br> the platform initialization flow<br>&nbsp;</span></p>)
@snapend


Note:

The PlatformInit folder (Intel/MinPlatformPkg/PlatformInit) - PlatformInitPei, PlatformInitDxe and PlatformInitSmm control the platform initialization flow. 

Because this flow needs to involve the board initialization,  there is a set of  board hook points defined in BoardInitLib (MinPlatformPkg/Include/Library/BoardInitLib.h) 



---?image=assets/images/slides/Slide37.JPG
@title[Hook - Board Detection ]
<p align="right"><span class="gold" >@size[1.1](<b>Hook - Board Detection </b>)</span><span style="font-size:0.75em;" ><br> - Kabylake example</span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
MinPlatformPkg/<br>&nbsp;&nbsp;
 . . .<br>&nbsp;&nbsp;
  PlatformInit/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei -&gt;  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         PlatformInitPreMem.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
			 @color[cyan](BoardDetect&lpar;&rpar;)<br>
KabylakeOpenBoardPkg/<br>&nbsp;&nbsp;
 . . .<br>&nbsp;&nbsp;
  KabylakeRvp3/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      BoardInitLib -&gt;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        PeiBoardInitPreMemLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
			 @color[cyan](BoardDetect&lpar;&rpar;)  <br>&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;
        PeiKabylakeRvp3Detect.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
			 @color[yellow](KabylakeRvp3BoardDetect&lpar;&rpar;)

<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<br>
<br>
<p style="line-height:65%" align="left" ><span style="font-size:0.7em; ">
Uses PCD Library calls to set / get Board SKU for Storing Board ID<br>
   <font face="Consolas">@size[.8em](LibPcdGetSku&lpar;&rpar; & LibPcdSetSku&lpar;&rpar;)</font><br><br>

<font face="Consolas">@size[.8em](KabylakeRvp3BoardDetect&lpar;&rpar;)</font> function reads Board ID from embedded controller (EC) using the LPC bus  <br><br>
@size[.8em](<font face="Consolas">LibPcdSetSku&lpar;&rpar;</font> stores Board ID)<br>
@size[.8em](<font face="Consolas">LibPcdGetSku&lpar;&rpar;</font> used from that point on)

<br>&nbsp;&nbsp;
</span></p>
@snapend



Note:



In order to determine which board specific driver needs to run and which does not need to run, there must be some code to detect the board type. 
The board detection code is board specific. It should be under the board specific directory 

Uses PCD calls to set / get Board Sku for Storing Board ID
	LibPcdGetSku() & LibPcdSetSku()

For the Kabylake example the lower function KabylakeRvp3BoardDetect() will read the ID from the EC using the LPC bus. 
Then is updates LibPcdSetSku() with the Board ID
LibPcdGetSku() can then be used elsewhere

The EC implements an embedded controller interface at ports 0x60/0x64 and a ACPI compliant
system management controller at ports 0x62/0x66. Port 0x66 is the command and status port,
port 0x62 is the data port.

Another NOTE: The SKU ID check should only happen in board specific drivers. The SKU ID check is NOT allowed in any common board code or common platform code. 


SkuIds is a special usage of PCD. It can support multiple configurations generated at build time, and it supports runtime selection to make one configuration take effect finally. 
Multi-sku PCD concept is defined by PI specification Volume 3, Chapter 8 PCD, EFI_PCD_PROTOCOL.SetSku () 


---
@title[Configuration Multi-SKU PCD – Board ID  ]
<p align="right"><span class="gold" >@size[1.1](<b>Configuration Multi-SKU PCD – Board ID </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-49 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-48 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](DSC File – SKU Set at BUILD time)
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;&nbsp;
 .&nbsp;.&nbsp;.<br>&nbsp;&nbsp;
SKUID_IDENTIFIER = ?<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[SkuIds]<br>&nbsp;&nbsp;
0|DEFAULT<br>&nbsp;&nbsp;
4|BoardX<br>&nbsp;&nbsp;
0x42|BoardY<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[PcdsDynamicDefault.common.@color[yellow](BoardX)]<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioPin|0x8<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioInitValue|\<br>&nbsp;&nbsp;&nbsp;&nbsp;
        &lbrace;0x00, 0x04, 0x02, 0x04, ...&rbrace;<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[PcdsDynamicDefault.common.@color[yellow](BoardY)]<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioPin|0x4<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioInitValue|\<br>&nbsp;&nbsp;&nbsp;&nbsp;
        &lbrace;0x00, 0x02, 0x01, 0x02, ...&rbrace;<br>&nbsp;&nbsp;
</span></p> 
@snapend


@snap[north-east span-47 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](SKU PCD Set Dynamically)
</span></p>
<br>
<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" >
&nbsp;&nbsp;
BoardXBoardDetect( VOID)<br>&nbsp;&nbsp;
&lbrace;<br>&nbsp;&nbsp;
. . .<br>&nbsp;&nbsp;&nbsp;&nbsp;
  if (@color[yellow](LibPcdGetSku) () != 0) &lbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    return EFI_SUCCESS;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &rbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;
  if (IsBoardX ()) &lbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     @color[yellow](LibPcdSetSku) (BoardIdIsBoardX);<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ASSERT (LibPcdGetSku() == <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              BoardIdIsBoardX);<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &rbrace;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  return EFI_SUCCESS;<br>&nbsp;&nbsp;
&rbrace;<br>&nbsp;&nbsp;
</span></p> 
@snapend



@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em">PCD Determines Board ID at Build time<br>&nbsp;</span></p>)
@snapend


Note:
SkuIds is a special usage of PCD. It can support multiple configurations generated at build time, and it supports runtime selection to make one configuration take effect finally. 

Multi-sku PCD concept is defined by PI specification Volume 3, Chapter 8 PCD, EFI_PCD_PROTOCOL.SetSku (). 

The SKU PCD is actually a dynamic PCD. During boot, the board detection takes the responsibility to set the SKU. Once the SKU PCD is set, the configuration associated with this SKU takes effect immediately 

---?image=assets/images/slides/Slide37.JPG
@title[Board Debug Initialization ]
<p align="right"><span class="gold" >@size[1.1](<b>Board Debug Initialization </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/KabylakeOpenBoardPkg/<br>&nbsp;
 . . .<br>&nbsp;
 KabylakeRvp3/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;
    BoardInitLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;
     PeiKabylakeRvp3InitPreMemLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       @color[yellow](KabylakeRvp3DebugInit&lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  		  @color[cyan](EarlySiliconInit&lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       . . .<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       @color[yellow](KabylakeRvp3BoardBootModeDetect&lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		 return <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		 BOOT_WITH_FULL_CONFIGURATION<br>&nbsp;&nbsp;<br>

Silicon/Intel/KabylakeSiliconPkg/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiliconInitLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      SiliconInitPreMem.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](EarlySiliconInit&lpar;&rpar;) <br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<br>
<p style="line-height:65%" align="left" ><span style="font-size:0.7em; ">
Once Board detection is successful, the next step is Board initialization. <br><br>
Kabylake example calls :
   <font face="Consolas">@size[.8em](EarlySiliconInit )</font>
   <br><br>
   - Early Platform PCH initialization<br><br>
   - Boot Mode Detect <br>&nbsp;&nbsp;– @size[.8em](example returns Boot with full <br>&nbsp;&nbsp;&nbsp;&nbsp;configuration )
</span></p>
@snapend



Note:


### Early Platform PCH initialization
- Program ACPI BASE
- Program PWRM BASE
- Program TCO BASE if it is present and not locked
- LPC I/O Configuration
- Enable the upper 128-byte bank of RTC RAM
- Disable the Watchdog timer expiration from causing a system reset 
- Halt the TCO timer
- Disable SERR NMI and IOCHK# NMI in port 61
- Program timer 1 as refresh timer

---?image=assets/images/slides/Slide37.JPG
@title[Board Init Before Memory Init]
<p align="right"><span class="gold" >@size[1.1](<b>Board Init Before Memory Init</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-51 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/KabylakeOpenBoardPkg/<br>&nbsp;
 . . .<br>&nbsp;
 KabylakeRvp3/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;
    BoardInitLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;
     PeiKabylakeRvp3InitPreMemLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       @color[yellow](KabylakeRvp3BoardInitBeforeMemoryInit&lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  		 KabylakeRvp3InitPreMem ()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  		 I2CGpioExpanderInitPreMem()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 		 GpioInitPreMem ()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 		 SioInit ()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		 @color[cyan](SiliconInit&lpar;&rpar;)<br>
Silicon/Intel/KabylakeSiliconPkg/<br>&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiliconInitLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      SiliconInitPreMem.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](SiliconInit&lpar;&rpar;) <br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-46 ]
<br><br>
<br>
<p style="line-height:65%" align="left" ><span style="font-size:0.7em; ">
Board Initialization before Memory Initialization
 <br><br><br><br>
The board specific initialization may include: 
</span></p>
@snapend


@snap[north span-5 ]
<br>
<br><br>
<br>
<br><br><br><br>
<br>
<ul style="list-style-type:none; line-height:0.7;">
  <li><span style="font-size:0.65em" >&nbsp;&nbsp;&nbsp;1. <br>&nbsp;</span> </li>
  <li><span style="font-size:0.65em" >&nbsp;&nbsp;&nbsp;2. <br>&nbsp;</span> </li>
  <li><span style="font-size:0.65em" >&nbsp;&nbsp;&nbsp;3. </span> </li>
</ul>
@snapend


@snap[north-east span-46 ]
<br>
<br>
<br><br><br><br>
<br><br>
<br>
<ul style="list-style-type:none; line-height:0.7;">
  <li><span style="font-size:0.65em" >Invoke a set of PCD for policy initialization later. </span> </li>
  <li><span style="font-size:0.65em" >Configure the hardware devices (such as GPIO, SIO) </span> </li>
  <li><span style="font-size:0.65em" >Silicon Initialization – i.e. PCH  </span> </li>
</ul>
@snapend



Note:

Once Board detection is successful, the next step is Board initialization. 
If the final BIOS image only needs to support one board, the board code can just implement a set of Board initialization API’s directly 



---?image=assets/images/slides/Slide37.JPG
@title[GPIOs – Stage 1]
<p align="right"><span class="gold" >@size[1.1](<b>GPIOs – Stage 1</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-51 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/KabylakeOpenBoardPkg/<br>&nbsp;
 . . .<br>&nbsp;
 KabylakeRvp3/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;
    BoardInitLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;
     PeiKabylakeRvp3InitPreMemLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       @color[yellow](KabylakeRvp3BoardInitBeforeMemoryInit&lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  		 KabylakeRvp3InitPreMem ()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  		 I2CGpioExpanderInitPreMem()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 		 @color[cyan](GpioInitPreMem &lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 		 SioInit ()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		 SiliconInit&lpar;&rpar;<br>
Silicon/Intel/KabylakeSiliconPkg/<br>&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    PeiDxeSmmGpioLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      GpioInit.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](GpioConfigureSklPch &lpar;&rpar;) <br>&nbsp;&nbsp;

<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-46 ]
<br><br>
<br>
<p style="line-height:65%" align="left" ><span style="font-size:0.7em; ">
If GPIOs need to be Initialized pre-memory then the hook <font face="Consolas">GpioInitPreMem()</font> calls the silicon library for GPIOs<br><br>
Example for Kabylake PCH GPIO pins
Table: <font face="Consolas">KabylakeRvp3GpioTable.c</font>
</span></p>
@snapend




Note:

procedure  GpioConfigurePads calls GpioConfigureSklPch()
 will initialize multiple GPIO pins. Use GPIO_INIT_CONFIG structure.
  Structure contains fields that can be used to configure each pad.
  Pad not configured using GPIO_INIT_CONFIG will be left with hardware default values.
  Separate fields could be set to hardware default if it does not matter, except
  GpioPad and PadMode.
  Some GpioPads are configured and switched to native mode by RC, those include:
  SerialIo pins, ISH pins, ClkReq Pins


---
@title[Silicon Policy – Stage 1]
<p align="right"><span class="gold" >@size[1.1](<b>Silicon Policy – Stage 1</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-51 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/MinPlatformPkg/<br>&nbsp;
 . . .<br>&nbsp;
 PlatformInit/<br>&nbsp;&nbsp;&nbsp;
  SiliconPolicyPei/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     SiliconPolicyPeiPreMem.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       @color[cyan](SiliconPolicyInitPreMem&lpar;&rpar;)<br><br>

Silicon/Intel/KabylakeSiliconPkg/<br>&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;
      PeiSiliconPolicyInitLibFsp<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         PeiFspPolicyInitLib.c  <br>&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;
          @color[cyan](SiliconPolicyInitPreMem&lpar;&rpar;)
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-46 ]
<br><br>
<br>
<p style="line-height:65%" align="left" ><span style="font-size:0.7em; ">
Performs silicon pre-mem policy initialization.<br><br>
The meaning of Policy is defined by silicon code.<br><br>
Input Policy should be <font face="Consolas">FspmUpd</font>. <br><br>
Value of FspmUpd has been initialized by FSP binary default value
<br><br>
</span></p>
@snapend

@snap[south-west span-40 fragment]
@box[bg-green-pp text-black waved my-box-pad2 ](<p style="line-height:70%" align="center"><span style="font-size:0.65em; " >@size[1.3em](FSP-M)<br>&nbsp;<br>Fsp Silicon Policy Update<br>Pre&nbsp;Mem<br>&nbsp;</span></p>)
@snapend



Note:
Performs silicon pre-memory policy update.

The meaning of Policy is defined by silicon code.

It could be the raw data, a handle, a PPI, etc.

The input Policy must be returned by SiliconPolicyDonePreMemory().

1) In FSP path, the input Policy should be FspmUpd.

A platform may use this API to update the FSPM UPD policy initialized
by the silicon module or the default UPD data.


The output of FSPM UPD data from this API is the final UPD data.


---
@title[Debug Configuration - Serial Port]
<p align="right"><span class="gold" >@size[1.1](<b>Debug Configuration - Serial Port</b>)</span><span style="font-size:0.75em;" ></span></p>

<p style="line-height:65%" align="left" ><span style="font-size:0.7em; ">
Serial port parameters come from the board and are used for debug features, serial input/output devices supporting local or remote consoles, and OS level debuggers<br><br>
Library – <font face="Consolas">@color[yellow](SerialPortLib)</font> find in workspace used by board .dsc<br><br>
Serial port configuration options consumed by <font face="Consolas">@color[yellow](SerialPortLib)</font> <br><br>
<font face="Consolas">@color[yellow](SerialPortLib)</font> is used by the <font face="Consolas">@color[yellow](StatusCodeHandlerPei.inf)</font> component to initialize and 
display messages to a serial port<br><br>
Serial port configuration options are published via @color[yellow](PCH_SERIAL_IO_CONFIG) used by <font face="Consolas">@color[yellow](PeiPchPolicyLib)</font>  <br>
&nbsp;&nbsp;&nbsp;&nbsp;<font face="Consolas">@size[.8em](Silicon/Intel/KabylakeSiliconPkg/Pch/Library/PeiPchPolicyLib)</font>
</span></p>

Note:

Serial port parameters come from the board
and are used for debug features, serial input/output devices supporting local or remote
consoles, and OS level debuggers

Serial port configuration options are consumed by the SerialPortLib library class implementation.
SerialPortLib library class is used by the StatusCodeHandlerPei.inf component to initialize and display messages to a serial port.

Find the SerialPortLib for the board code
To find the Libraries for the Platform specific code
1. Search the Work space .DSC files for the string of the library
2. Open the .DSC files associated with the platform
3. Determine which Library is used and that should have the build path in the workspace.

Kabylake uses SerialPortLib default core from MdeModulePkg/Library/BaseSerialPortLib16550/BaseSerialPortLib16550.inf
Kabylake uses StatusCodeHandlerPei from MdeModulePkg/Universal/StatusCodeHandler/Pei/StatusCodeHandlerPei.inf

Find library for creating Serial for the Hobs to pass to next phase. For Kabylake it is PCH_SERIAL_IO_CONFIG used by PeiPchPolicyLib for Hobs  located: Silicon/Intel/KabylakeSiliconPkg/Pch/Library/PeiPchPolicyLib

The PCH_SERIAL_IO_CONFIG block provides the configurations to set the Serial IO controllers
  to Acpi devices or Pci controllers, and also set the interrupt type to Acpi or Pci
  through Policy.


---
@title[Debug Configuration PCDs - Serial Port]
<p align="right"><span class="gold" >@size[1.1](<b>Debug Configuration PCDs - Serial Port</b>)</span><span style="font-size:0.75em;" ></span></p>



@snap[north-west span-100 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>

<p style="line-height:45%" align="left" ><span style="font-size:0.4em; font-family:Consolas;"><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialBaudRate - <font face="Arial">Baud rate for the 16550 serial port</font><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialUseMmio - <font face="Arial">Enable serial port MMIO addressing </font><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialUseHardwareFlowControl - <font face="Arial">Enable serial port HW flow control  </font><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialDetectCable - <font face="Arial">Enable blocking Tx if no cable  </font><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialRegisterBase - <font face="Arial">Register the serial port base address </font><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialLineControl - <font face="Arial">Serial port line control configuration  </font><br>
gEfiMdeModulePkgTokenSpaceGuid.PcdSerialFifoControl - <font face="Arial">Serial port FIFO control  </font><br>
gMinPlatformPkgTokenSpaceGuid.PcdSecSerialPortDebugEnable - <font face="Arial">Enable serial port debug in SEC phase </font><br>
<br>
<br>
<br>
<font face="Arial">@size[1.4em](Debug configuration PCDs) </font><br>
gEfiMdePkgTokenSpaceGuid.PcdFixedDebugPrintErrorLevel - <font face="Arial">Control optimization based on debug print level - messaage type</font><br>
gEfiMdePkgTokenSpaceGuid.PcdDebugPropertyMask - <font face="Arial">Control DebugLib behavior  </font><br>
gEfiMdePkgTokenSpaceGuid.PcdDebugPrintErrorLevel - <font face="Arial">Control run time debug print level </font><br>
gEfiMdePkgTokenSpaceGuid.PcdReportStatusCodePropertyMask - <font face="Arial">Control display of status codes </font><br>
</span></p>
@snapend


Note:

slide show the PCDs for the serial port for configuration 

also shown are the debug configuration PCDs


---
@title[Stage 1 Checklist ]
<p align="center"><span class="gold" >@size[1.1](<b>Stage 1 Checklist </b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; ">Steps to enable a board for Stage 1.
</span></p>

@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

@snap[north-east span-98 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.7em; "> <br><br>
 1. Copy the EDK II packages to a local workspace  <br>
 2. Select the correct Intel® FSP & review requirements  <br>
 3. Get silicon initialization requirements for the given board. <br>
 4. Customize the silicon initialization solution to the board-specific <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;requirements. <br>
 5. Determine other firmware and software components <br>
 6. Determine board-specific information required to fetch code and <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show debug output. <br>
 7. Copy a reference <font face="Consolas">@size[.8em](GenerationOpenBoardPkg/BoardXxx)</font> and update the <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;board interfaces in Required Functions. <br>
   &nbsp;&nbsp;&nbsp;&nbsp;- serial port initialization code in <font face="Consolas">@size[.8em](PlatformHookSerialPortInitialize &lpar;&rpar;)</font> at<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <font face="Consolas">@size[.8em](BoardPkg/Library/BasePlatformHookLib.)</font> <br>
   &nbsp;&nbsp;&nbsp;&nbsp;- Add Board detection code in <font face="Consolas">@size[.8em](BoardDetect &lpar;&rpar;)</font>
</span></p>
@snapend

Note:

Steps to enable a board for Stage I.
Copy the EDK II packages locally to the workspace.
Select silicon initialization solution .i.e. Intel® FSP. & Review the requirements for the silicon initialization solution.
Gather the silicon initialization requirements for the given board.
Customize the silicon initialization solution to configure the system to the board-specific requirements
  - For Intel® FSP, this includes setting minimal policy configuration.
  - For other silicon solutions, similar parameter customization may be needed if the silicon solution is not written for a particular system design.
6, Determine other firmware and software components required for the system to function properly.
  - For an Intel platform, this may include firmware images such as the appropriate microcode patch, EC firmware image, power management controller firmware, and others.
  - Additional third-party add-in components such as specific UEFI drivers may also be required.
7. Determine board-specific information required to fetch code and show debug output.
  - This includes details such as the NVRAM layout and strap information.
8. Copy a reference GenerationOpenBoardPkg/BoardXXX and update the board
interfaces in Required Functions.
  - Add serial port initialization code in PlatformHookSerialPortInitialize () at 				BoardPkg/Library/BasePlatformHookLib.
  - This is SIO related code.
ii. Add Board detection code in BoardDetect ()


BoardPkg/BoardInitLib/PeiBoardXXXInitPreMemoryLib.c`
If the project only supports one board, this function can return directly.
2. Add Board pre-memory debug initialization code in BoardDebugInit () ,
BoardPkg/BoardInitLib/PeiBoardXXXInitPreMemoryLib.c.
i. This is for debug channel related initialization.
3. Audit BoardPkg/Stage1.dsc, ensure all PCDs in the Configuration section are correct for
your board.
i. Set gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 1
ii. Follow "Debug Lib Selection" to enable serial debug capability.
4. Audit all other PCD settings in the board DSC file to verify the values are correct for
your board.
5. Verify the flash layout is compliant with this specification.
6. Verify the required binaries will be included in the image produced in the build.
7. Verify the code execution path for Stage I will only perform the actions required to
achieve debug output.
8. Boot the system, collect the debug log, and verify the test point results are correct.



---
@title[Stage 1 Checklist 02 ]
<p align="center"><span class="gold" >@size[1.1](<b>Stage 1 Checklist<br>- Board Pre-mem Lib </b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; ">
Kabylake -<br>
<font face="Consolas">@size[.7em](KabylakeOpenBoardPkg/KabylakeRvp3/Library/BoardInitLib/@color[yellow](PeiBoardInitPreMemLib))</font>
</span></p>

@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

@snap[north-east span-98 ]
<br>
<br>
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.7em; "> <br>
 1. Add Board pre-memory debug initialization code in <font face="Consolas">@size[.8em](BoardDebugInit&lpar;&rpar;)</font>  <br>
 2. Ensure all PCDs in the Configuration section are correct (i.e. Serial debug) <br>
 3. Verify values of other PCDs are correct <br>
 4. Verify the flash layout is compliant <br>
 5. Verify the required binaries  included in the build <br>
 6. Verify debug output during the code execution path for Stage 1 <br>
 7. Verify the test point results  are correct <br>
</span></p>

<p style="line-height:70%" align="left" ><span style="font-size:0.45em; ">
<a href="https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/3_stage_1_minimum_debug/39_test_point_results.html">EDK II Open Platform Spec Test points Stage 1</a>
</span></p>

@snapend

Note:
BoardPkg/BoardInitLib/PeiBoardXXXInitPreMemoryLib.c`

1. If the project only supports one board, this function can return directly.
2.  Add Board pre-memory debug initialization code in BoardDebugInit () , BoardPkg/BoardInitLib/PeiBoardXXXInitPreMemoryLib.c. - This is for debug channel related initialization.
3.  Audit BoardPkg/Stage1.dsc, ensure all PCDs in the Configuration section are correct for
your board. - Set gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 1 and  Follow "Debug Lib Selection" to enable serial debug capability.
4. Audit all other PCD settings in the board DSC file to verify the values are correct for
your board.
5. Verify the flash layout is compliant with this specification.
6. Verify the required binaries will be included in the image produced in the build.
7. Verify the code execution path for Stage I will only perform the actions required to
achieve debug output.
8. Boot the system, collect the debug log, and verify the test point results defined in the
Test Point section are correct.

---?image=assets/images/slides/Slide_TableDHote.JPG
@title[Staged Approach by Features Section 02 ]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>


@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 1&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Enable Debug &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Stage 2&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Memory Initialization)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 3&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot to UEFI Shell only &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 4&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 5&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS w/ Security enabled&nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 6&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Advanced Feature Selection)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 7&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Performance Opetimizations &nbsp;)</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations



---?image=assets/images/slides/Slide46.JPG
@title[Boot Flow – Stage 2]
<p align="right"><span class="gold" >@size[1.1](<b>Boot Flow – Stage 2</b>)</span><span style="font-size:0.75em;" ></span></p>


Note:

 The objective of Stage II is to enable a minimal boot path memory initialization code execution that successfully installs permanent memory.



---?image=assets/images/slides/Slide47.JPG
@title[High Level Control Flow – Stage 2]
<p align="right"><span class="gold" >@size[1.1](<b>High Level Control Flow – Stage 2</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-58 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.85em; "><br>
Major Execution Activities
</span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" > Complete execution of the memory initialization module</span> </li>
  <li><span style="font-size:0.65em" > Discover, train and install permanent memory </span> </li>
  <li><span style="font-size:0.65em" > Migrate the temporary memory/stack to permanent memory.</span> </li>
  <li><span style="font-size:0.65em" > Migrate any code modules from temporary RAM to permanent memory.</span> </li>
  <li><span style="font-size:0.65em" > Perform cache configuration for a post-memory environment.</span> </li>
  <li><span style="font-size:0.65em" > Execute memory installed notification actions.</span> </li>
</ul>
@snapend

Note:

Stage II extends the Stage I control flow by executing the platform and silicon initialization required for memory initialization. The stage is completed when permanent memory is installed. Since execution prior to memory initialization typically occurs in a resource-constrained environment, the code in this stage is not compressed. To simplify silicon enabling which may be opaque to the board engineer in the form of a binary blob, Stage II enabling does not strictly constrain the extent of silicon initialization. In particular, it is recommended to perform standard security lock functionality such as register locks, privilege level changes, and other actions that are in the system requirements to reduce conditional logic and therefore potential for error in enabling those settings. This only pertains to security settings within the chipset. This does not include larger industry standard security features such as UEFI Secure Boot and TCG measured boot. Those features are enabled in Stage V Security Enable.

#### Stage II functionality:
- Non-volatile storage read-only access
- Pre-memory silicon policy initialization - Basic services like cache and CPU IO
- Initialization of decompression capability
- Memory initialization and basic memory test  


---
@title[Stage 2 Firmware Volumes]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 2 Firmware Volumes</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Name&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Content</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvPostMemory&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Post-memory modules&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspM&nbsp;</span></p></td>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Memory initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;-&gt;FvPreMemorySilicon&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Pre-memory silicon initialization&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvFspS&nbsp;</span></p></td>
		<td bgcolor="#323232" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Silicon initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;-&gt;FvPostMemorySilicon&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".0%2"><p style="line-height:01%"><span style="font-size:0.5em" >Post-memory silicon initialization &nbsp;</span></p></td>
	</tr>
</table>
<br>
@snapend



Note:

Stage II leverages most of the Stage I content.
Notice FvFspM is in both Stage 1 and stage 2




---
@title[Stage 2 FVs Contents]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 2 FVs Contents</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>FV&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Components</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Purpose</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvPostMemory&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >PlatformInitPostMem.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".020%" width="70%"><p style="line-height:022%"><span style="font-size:0.45em" >Performs post memory initialization		&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >FspsWrapperPeim.efi &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >Calls FSP-M & FSP-S FV </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPolicyPeiPostMem.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >Publishes silicon initialization configuration </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > DxeIpl.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" > Load and invoke DXE</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >. . . &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" > &nbsp;</span></p></td>
	</tr>

</table>
<br>
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Mapped according to .FDF file layout<br><br>&nbsp;</span></p>)
@snapend


Note:

Main purpose is to initialize memory.
Example show Kabylake with FSP wrapper to call the FSP MemoryInit function inside FSP module.


---
@title[Stage 2 Platform Libraries - PEI]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 2 Platform Libraries - PEI</b>)</span><span style="font-size:0.75em;" ></b></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable-1">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Item</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>API Definition</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Producing Pkg</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Description</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardInitLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:01%"><span style="font-size:0.4em" > Board initialization library. </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPolicyInitLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > IntelSiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:020%"><span style="font-size:0.4em" > Provides default silicon configuration policy data. </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:020%"><span style="font-size:0.4em; font-family:Consolas;" > SiliconPolicy UpdateLib &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > IntelSiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > BoardPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:020%"><span style="font-size:0.4em" >  Provides board updates to silicon configuration policy data.</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > TestPointCheckLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:020%"><span style="font-size:0.4em" >  Test point check library.</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > TestPointLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:020%"><span style="font-size:0.4em" >  Test point library.</span></p></td>
	</tr>
</table>
<br>
@snapend




Note:

BoardInitLib 
-  MinPlatformPkg - BoardPkg  - Board initialization library.
SiliconPolicyInitLib 
 - IntelSiliconPkg SiliconPkg Provides default silicon configuration policy data.
SiliconPolicyUpdateLib 
- IntelSiliconPkg BoardPkg Provides board updates to silicon configuration policy data.
TestPointCheckLib 
- MinPlatformPkg MinPlatformPkg Test point check library. It is called by PlatformInit module to perform stagespecific checks.
TestPointLib 
MinPlatformPkg MinPlatformPkg Test point library. It provides helper functionality for TestPointCheck lib.


---
@title[Stage 2 Platform Libraries - DXE]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 2 Platform Libraries - DXE</b>)</span><span style="font-size:0.75em;" ></b></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable-1">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Item</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>API Definition</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Producing Pkg</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Description</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  ResetSystemLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  MdeModulePkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  SiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:01%"><span style="font-size:0.4em" >  For DXE reset architecture protocol</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  PciHostBridgeLib&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  MdeModulePkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  SiliconPkg&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:01%"><span style="font-size:0.4em" > For DXE PCI host bridge driver </span></p></td>
	</tr>
</table>
<br>
@snapend




Note:
Stage II contains some DXE items needed to enable Stage III. No board porting of these libraries is required. Board integrators should ensure that their silicon package provides the necessary libraries. These libraries and the UEFI Components (DXE) are functionally irrelevant to Stage II functionality.

ResetSystemLibSilicon/ Intel /KabylakeSiliconPkg/Pch/Library/DxeRuntimeResetSystemLib/DxeRuntimeResetSystemLib

PciHostBridgeLib

- Kabylake:
   - MinPlatformPkg\Pci\Library\PciHostBridgeLibSimple\PciHostBridgeLibSimple
  used in \MdeModulePkg\Bus\Pci\PciHostBridgeDxe\PciHostBridgeDxe



---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules - Stage 2 ]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules <br>- Stage 2</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
MinPlatformPkg/<br>&nbsp;&nbsp;
  Include/<br>&nbsp;&nbsp;&nbsp;&nbsp;
     Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	   @color[yellow](BoardnitLib.h)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	   @color[yellow](SiliconPolicyInitLib.h)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	   @color[yellow](SiliconPolicyUpdateLib.h)<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;
  . . .<br>&nbsp;&nbsp;
  PlatformInit/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PlatformInitPreMem/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  PlatformInitPostMem/<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-46 ]
<br>
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
BoardBootModeDetect&lpar;&rpar;<br>
BoardInitBeforeMemoryInit&lpar;&rpar;<br>
<br>
MemoryInit&lpar;&rpar;<br>
<br>
SiliconPolicyInitPreMemory&lpar;&rpar;<br>
SiliconPolicyUpdatePreMemory&lpar;&rpar;<br>
SiliconPolicyDonePreMemory&lpar;&rpar;<br>
<br>&nbsp;&nbsp;
</span></p>
@snapend



Note:

The PlatformInit folder (Intel/MinPlatformPkg/PlatformInit) - PlatformInitPei, PlatformInitDxe and PlatformInitSmm control the platform initialization flow. Because this flow needs to involve the board initialization,  there is a set of  board hook points defined in BoardInitLib (MinPlatformPkg/Include/Library/BoardInitLib.h) 



---
@title[Platform Initialization Memory Init]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Memory Init</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
<font color="gray">edk2-platforms/<br>&nbsp;
Platform/Intel/MinPlatformPkg/<br>&nbsp;&nbsp;
 . . .<br>&nbsp;&nbsp;
 PlatformInit/<br>&nbsp;&nbsp;&nbsp;
  PlatformInitPei/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;;&nbsp;
     PlatformInitPreMem.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformInitPostMem.c<br>
	 <br><br></font>
edk2/<br>&nbsp;&nbsp;
  FspIntelFsp2WrapperPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    FspmWrapperPeim/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      @color[yellow](FspMemoryInitApi&lpar;&rpar;)
<br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br><br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
<font face="Arial"> Notify call back </font><br>&nbsp;&nbsp;
  @color[yellow](BoardInitAfterMemoryInit&lpar;&rpar;)
</span></p>
@snapend

@snap[south-east span-40 fragment]
@box[bg-green-pp text-black waved my-box-pad2 ](<p style="line-height:70%" align="center"><span style="font-size:0.65em; font-family:Consolas;" >@size[1.3em](FSP-M)<br>&nbsp;<br> FspMemoryInitApi&lpar;&rpar;<br><br>&nbsp;</span></p>)
<br>
<br>
@snapend



Note:

Memory Initialization  done using the FSP Memory Init API through the FSP wrapper.


---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
MinPlatformPkg/<br>&nbsp;&nbsp;
 . . .<br>&nbsp;&nbsp;
 PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[gray](PlatformInitPreMem)/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[yellow](PlatformInitPostMem)/ <br>&nbsp;&nbsp;
 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    @color[cyan](BoardInitBeforeSiliconInit&lpar;&rpar; )<br>&nbsp;&nbsp;
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitEndOfPei() <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     BoardInitAfterSiliconInit() <br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br><br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
KabylakeOpenBoardPkg/ <br>&nbsp;&nbsp;
 KabylakeRvp3/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   BoardInitLib/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PeiKabylakeRvp3InitPostMemLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](KabylakeRvp3)\ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](BoardInitBeforeSiliconInit&lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		  ConfigureGpio() <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		    . . . <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		  LateSiliconInit() <br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Hook for Before Silicon Initialization<br><br>&nbsp;</span></p>)
@snapend

Note:


From the Kabylake FDF PlatformInitPostMem module has 
 BoardInitBeforeSiliconInit()
    PlatformInitEndOfPei()
     BoardInitAfterSiliconInit()

And the Platform Libs to go with this are in edk2-platforms\Platform\Intel\
KabylakeOpenBoardPkg\KabylakeRvp3\Library\BoardInitLib\PeiKabylakeRvp3InitPostMemLib.c

With call to: KabylakeRvp3BoardInitBeforeSiliconInit()



---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules 02]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
MinPlatformPkg/<br>&nbsp;&nbsp;
 . . .<br>&nbsp;&nbsp;
 PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[gray](PlatformInitPreMem)/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[yellow](PlatformInitPostMem)/ <br>&nbsp;&nbsp;
 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    @color[gray](BoardInitBeforeSiliconInit&lpar;&rpar; )<br>&nbsp;&nbsp;
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitEndOfPei() <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      @color[cyan](BoardInitAfterSiliconInit&lpar;&rpar; ) <br>&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br><br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
KabylakeOpenBoardPkg/ <br>&nbsp;&nbsp;
 KabylakeRvp3/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   BoardInitLib/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PeiBoardInitPostMemLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](BoardInitAfterSiliconInit&lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Hook for After Silicon Initialization<br><br>&nbsp;</span></p>)
@snapend

Note:


Same but now for BoardInitAfterSilicon
From the Kabylake FDF PlatformInitPostMem module has 
 BoardInitBeforeSiliconInit()
    PlatformInitEndOfPei()
     BoardInitAfterSiliconInit()

And the Platform Libs to go with this are in edk2-platforms\Platform\Intel\
KabylakeOpenBoardPkg\KabylakeRvp3\Library\BoardInitLib\PeiBoardInitPostMemLib.c

For Kabylake just returns EFI_SUCCESS



---?image=assets/images/slides/Slide37.JPG
@title[FSP Wrapper for Silicon Initialization ]
<p align="right"><span class="gold" >@size[1.1](<b>FSP Wrapper for Silicon Initialization </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-98 ]
<br><br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
edk2/<br>&nbsp;&nbsp;
  FspIntelFsp2WrapperPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    FspmWrapperPeim/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      @color[yellow](PeiMemoryDiscovredNotify&lpar;&rpar;)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <font face="Arial">Finish Memory Migration</font>   <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <font face="Arial">--&gt;FSP Silcon Init API </font><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](PostFspHobProcess&lpar;&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-47 ]
<br><br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
MinPlatformPkg/FspWrapper/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;
   PeiFspWrapperHobProcessLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    FspWrapperHobProcessLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      @color[cyan](PostFspsHobProcess&lpar;&rpar;)
</span></p>
@snapend

@snap[south-east span-40 fragment]
@box[bg-green-pp text-black waved my-box-pad2 ](<p style="line-height:70%" align="center"><span style="font-size:0.65em; font-family:Consolas;" >@size[1.3em](FSP-S)<br>&nbsp;<br> FspSiliconInitApi&lpar;&rpar;<br><br>&nbsp;</span></p>)
<br>
<br>
@snapend



Note:

 FSP Wrapper is used to call into the FSP-S for the FspSiliconInit API.

---
@title[Silicon Policy Update Lib ]
<p align="right"><span class="gold" >@size[1.1](<b>Silicon Policy Update Lib </b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[north-west span-95 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em; ">
Using the <font face="Consolas">@color[yellow](SiliconPolicyUpdateLib)</font>, the board package may reference a variety of sources to obtain the board-specific policy values
</span></p>
<ul style="list-style-type:none; line-height:0.7;">
    <li><span style="font-size:0.7em" >1.&nbsp; PCD database  </span> </li>
    <li><span style="font-size:0.7em" >2.&nbsp; UEFI Variable </span> </li>
    <li><span style="font-size:0.7em" >3.&nbsp; Binary Blob </span> </li>
    <li><span style="font-size:0.7em" >4.&nbsp; Built-in C structure </span> </li>
    <li><span style="font-size:0.7em" >5.&nbsp; Hardware information </span> </li>
</ul>
@snapend




@snap[east span-24 ]
<br><br>
![SiliconPolicyLib](/assets/images/SiliconPolicyLib.png)
@snapend



@snap[south span-100 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">One silicon policy data structure created per silicon module<br><br>&nbsp;</span></p>)
<br>
@snapend


Note:

One silicon policy data structure is created per silicon module. The data structure should
only contain data. Functions should not be used in silicon policy data.
When a silicon module installs this policy data, it should consider the most common usage
as the default policy data. Therefore, a board module must only update non-default values
instead of all fields.

http://infodome.wikidot.com/local--files/rules-of-combat-dome/rule_book1.gif


---
@title[Silicon Policy APIs ]
<p align="right"><span class="gold" >@size[1.1](<b>Silicon Policy APIs </b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[north-west span-75 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.9em; ">
Silicon code exposes  APIs to:
</span></p>
<ul style="list-style-type:disc; line-height:0.75;">
    <li><span style="font-size:0.8em" > Initialize all policy data to the default value, based upon the current silicon. </span> </li>
    <li><span style="font-size:0.8em" > Inform silicon code that all policy data have been updated, and they are ready to consume. </span> </li>
</ul>
@snapend




@snap[east span-24 ]
<br><br>
![API_Pic](/assets/images/API_Pic.png)
@snapend



@snap[south span-100 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Board module only updates non-default values<br><br>&nbsp;</span></p>)
<br>
@snapend


Note:

http://mathinsight.org/media/image/image/function_machine.png

This silicon code may expose the APIs:
An API to initialize all policy data to the default value, based upon the current silicon.
An API to tell silicon code that all policy data have been updated, and they are ready to consume.

a board module must only update non-default values
instead of all fields.








---?image=assets/images/slides/Slide58.JPG
@title[FSP Silicon Policy Data Flow ]
<p align="right"><span class="gold" >@size[1.1](<b>FSP Silicon Policy Data Flow</b>)</span><span style="font-size:0.75em;" ></span></p>



Note:
Slide from: https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification 4.6.1.5 Intel® FSP Policy Data Flow


After policy configuration is completed, the board may indicate that the policy is configured
with board-specific actions in the SiliconPolicyDonePreMemory ( ) API in SiliconPolicyInitLib

<pre>
UpdateFspmUpdData (Upd)
SiliconPolicyInitPreMemory ()
SiliconPolicyUpdatePreMemory ()
Minimum platform: Minor update of relevant options
Fully featured platform (Stage VI and greater): Full update for all platform features
SiliconPolicyDonePreMemory ()
</pre>




---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Silicon]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Silicon</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
  . . . <br>&nbsp;&nbsp;
  PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 <br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiliconPolicyPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       SiliconPolicyPeiPostMem.c <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         SiliconPolicyPeiPostMemEntrypoint() <br> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[cyan](SiliconPolicyInitPostMem &lpar;&rpar;)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](SiliconPolicyUpdatePostMem&lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](SiliconPolicyDonePostMem&lpar;&rpar;) 
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Silicon/Intel/<br>
KabylakeSiliconPkg/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    PeiSiliconPolicyInitLibFsp/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiFspPolicyInitLib.c <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](SiliconPolicyInitPostMem&lpar;&rpar;) <br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <font face="Arial">// Using the FSP Update policy  </font> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[yellow](PeiFspPchPolicyInit &lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[yellow](PeiFspMePolicyInit &lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[yellow](PeiFspSaPolicyInit &lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[yellow](PeiFspCpuPolicyInit &lpar;&rpar;) 
</span></p>
@snapend





@snap[south span-100 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Example: Kabylake - post-mem FSP Silicon Init<br><br>&nbsp;</span></p>)
@snapend


Note:

Kabylake example:
Slide show location of the Platform vs. silicon modules corresponding to the Silicon Policy updates after memory init. 

Platform calls silicon module relying on the FSP code to manage the underling data structures.


---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Silicon 02]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Silicon</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
  . . . <br>&nbsp;&nbsp;
  PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 <br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiliconPolicyPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       SiliconPolicyPeiPostMem.c <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         SiliconPolicyPeiPostMemEntrypoint() <br> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[gray](SiliconPolicyInitPostMem &lpar;&rpar;)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[cyan](SiliconPolicyUpdatePostMem&lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](SiliconPolicyDonePostMem&lpar;&rpar;) 
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
KabylakeOpenBoardPkg/<br>&nbsp;&nbsp;
  FspWrapper/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiSiliconPolicyUpdateLibFsp/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        PeiFspPolicyUpdateLib.c <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[cyan](SiliconPolicyUpdatePostMem&lpar;&rpar;) <br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[yellow](PeiFspSaPolicyUpdate &lpar;&rpar;)        <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[yellow](PeiFspPchPolicyUpdate &lpar;&rpar;) 
</span></p>
@snapend





@snap[south span-100 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Notice the Update is from board FSP Wrapper Library<br><br>&nbsp;</span></p>)
@snapend


Note:

Notice the Update Post mem is from the Kabylake FSP wrapper and not the silicon.

This is because the previous slide (init) already  got the FSP API pointer so the board can now just do the update.


Performs silicon post-mem policy update.

  The meaning of Policy is defined by silicon code.
  It could be the raw data, a handle, a PPI, etc.
  
  The input Policy must be returned by SiliconPolicyDonePostMem().
  
  1) In FSP path, the input Policy should be FspsUpd.
  A platform may use this API to update the FSPS UPD policy initialized
  by the silicon module or the default UPD data.
  The output of FSPS UPD data from this API is the final UPD data.


---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Silicon 03]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Silicon</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
  . . . <br>&nbsp;&nbsp;
  PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 <br>&nbsp;&nbsp;&nbsp;&nbsp;
    SiliconPolicyPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       SiliconPolicyPeiPostMem.c <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         SiliconPolicyPeiPostMemEntrypoint() <br> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[gray](SiliconPolicyInitPostMem &lpar;&rpar;)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[gray](SiliconPolicyUpdatePostMem&lpar;&rpar;) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[cyan](SiliconPolicyDonePostMem&lpar;&rpar;) 
</span></p>
@snapend

@snap[north-east span-47 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Silicon/Intel/<br>
KabylakeSiliconPkg/<br>&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;
    PeiSiliconPolicyInitLibFsp/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PeiFspPolicyInitLib.c <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        @color[cyan](SiliconPolicyDonePostMem&lpar;&rpar;) <br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 </span></p>
@snapend




@snap[south span-100 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Silicon post-mem policy is finalized<br><br>&nbsp;</span></p>)
@snapend


Note:

The silicon post-mem policy is finalized.
  Silicon code can do initialization based upon the policy data.

  The input Policy must be returned by SiliconPolicyInitPostMem().
 
---
@title[Prepare for Hand-off to DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Prepare for Hand-off to DXE</b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[north-east span-70 ]

<p style="line-height:20%" align="left" ><span style="font-size:0.7em;" ><br><br><br>&nbsp;</span></p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-31 ]
<p style="line-height:20%" align="left" ><span style="font-size:0.7em;" ><br><br><br>&nbsp;</span></p>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><br><b>Hob Output</b><br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><b>MTRR <br>Configuration</b><br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><br><b>DXE IPL</b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-67 ]
<p style="line-height:20%" align="left" ><span style="font-size:0.7em;" ><br><br><br><br><br><br>&nbsp;</span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.67em;" >&bull; 2 Hob lists - FSP &  FSP Wrapper<br><br><br><br></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.67em;" >&bull; 2 locations – after permanent Memory & Prior to <br>&nbsp;&nbsp;&nbsp; DXE IPL platform's capabilities <br><br><br><br> </span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.67em;" >&bull; Load and invoke DXE <br><br><br><br> </span></p>

@snapend


Note:

Intel® FSP HOB to PEI HOB transition


In an Intel® FSP API mode boot with an EDK II wrapper, the system will have two HOB
lists - one maintained in the FSP PEI environment and the other in the FSP wrapper PEI
environment. The FSP wrapper environment is responsible for converting data from the
FSP HOB to a PEI HOB. These HOBs are platform-specific; examples include the
SmbiosHob and GraphicInfoHob.


MTRR Configuration Settings in Post-Memory
The system MTRR settings are typically configured in two locations after permanent memory
initialization.


1. After permanent memory installation


At this point, cache attributes are set for PEI memory usage. This specification does not
require any particular MTRR configuration, as it is ultimately dependent upon platform
goals such as functionality and performance given the device and storage technologies
present on the platform. The most common ranges configured are the default memory
setting as UC, the DRAM region as WB, and the SPI flash MMIO region as WP. These
settings are usually applied in a memory installation notification function or a PEIM
shadow. The architecture requires that the settings be applied in the board package.


2. Prior to DXE IPL


At this point PEI execution has completed and control is transitioning to the DXE phase.
The MTRR settings are typically modified to prepare for the DXE environment. The
most common ranges configured are the default memory as WB, the TSEG (SMRAM)
region as UC, and MMIO as UC. These settings are usually applied in an end of PEI
notification function. The architecture requires that the settings be applied in the board
package.



---
@title[Stage 2 Checklist  ]
<p align="center"><span class="gold" >@size[1.1](<b>Stage 2 Checklist</b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; ">
Steps to enable a board for Stage 2.
</span></p>

@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

@snap[north-east span-98 ]
<br>
<br>
<br>
<ul style="list-style-type:None; line-height:0.7;">
  <li><span style="font-size:0.65em" >1. Update <font face="Consolas"><i>@color[cyan](NewOpenBoardPkg/BoardXxx) </i></font></span> </li>
  <ul style="list-style-type:disc; line-height:0.6;">
      <li><span style="font-size:0.55em" > Add Board boot mode detection code in BoardBootModeDetect () , <font face="Consolas">@color[yellow](BoardXXX/BoardInitLib/PeiBoardXxxInitPreMemoryLib.c.)</font> </span> </li>
      <ul style="list-style-type:none; line-height:0.5;">
        <li><span style="font-size:0.5em" > - The boot mode can be hardcoded. It should reflect actual functionality based upon<br>&nbsp;&nbsp;&nbsp;
             the feature, such as S3 (silicon register), Capsule (variable), Recovery(GPIO). </span> </li>
      </ul>
      <li><span style="font-size:0.55em" > Add Board pre-memory initialization code in <font face="Consolas">@color[yellow](BoardInitBeforeMemoryInit &lpar;&rpar;) and @color[yellow](BoardInitAfterMemoryInit &lpar;&rpar; , BoardXxx/BoardInitLib/PeiBoardXxxInitPreMemLib.c.)</font> </span> </li>
      <ul style="list-style-type:none; line-height:0.5;">
        <li><span style="font-size:0.5em" > - It initializes board specific hardware devices, such as GPIO.</span> </li>
        <li><span style="font-size:0.5em" > - It also updates pre-memory policy configuration by using PCD </span> </li>
      </ul>
      <li><span style="font-size:0.55em" > Add Board policy update code in <font face="Consolas">@color[yellow](SiliconPolicyUpdatePreMemory &lpar;&rpar; , BoardXxx/PeiSiliconPolicyUpdateLib/PeiBoardXxxInitPreMemoryLib.)</font> </span> </li>
      <ul style="list-style-type:none; line-height:0.5;">
        <li><span style="font-size:0.5em" > - The PCD updated in <font face="Consolas">@color[yellow](BoardInitBeforeMemoryInit &lpar;&rpar; ) </font>might be used here. </span> </li>
      </ul>
  </ul>
  <li><span style="font-size:0.65em" >2.  Ensure all PCDs in the configuration section (DSC files) are correct for your 
    <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;board. </span> </li>
  <li><span style="font-size:0.65em" >3.  Ensure all required binaries in the flash file (FDF files) are correct for your 
    <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;board .</span> </li>
 
  <li><span style="font-size:0.65em" >4. Boot, collect log, verify test point results are correct.  </span> </li>
 
</ul>
<p style="line-height:70%" align="left" ><span style="font-size:0.45em; ">
<a href="https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/4_stage_2_memory_functional/49_test_point_results.html">EDK II Open Platform Spec Test points Stage 2</a>
</span></p>

@snapend


Note:

Steps to enable a board for Stage II
1.  Update the NewOpenBoardPkg/BoardXXX
  i. Add Board boot mode detection code in BoardBootModeDetect () ,    BoardXXX/BoardInitLib/PeiBoardXXXInitPreMemoryLib.c.
     i. The boot mode can be hardcoded. It should reflect actual functionality based upon the feature, such as S3 (silicon register), Capsule (variable), Recovery (GPIO).
  ii. Add Board pre-memory initialization code in BoardInitBeforeMemoryInit () and BoardInitAfterMemoryInit () , BoardXXX/BoardInitLib/PeiBoardXXXInitPreMemLib.c.
  i. It initializes board specific hardware devices, such as GPIO.
  ii. It also updates pre-memory policy configuration by using PCD
  iii. Add Board policy update code in SiliconPolicyUpdatePreMemory () ,

BoardXXX/PeiSiliconPolicyUpdateLib/PeiBoardXXXInitPreMemoryLib.c.
  i. The PCD updated in BoardInitBeforeMemoryInit () might be used here.
2. Ensure all PCDs in the configuration section (DSC files) are correct for your board.
  i. Set gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 2
3. Ensure all required binaries in the flash file (FDF files) are correct for your board.
4. Boot, collect log, verify test point results defined in section 4.9 from the EDK II Open Platform spec are correct.



---?image=assets/images/slides/Slide_TableDHote.JPG
@title[Staged Approach by Features Section 03 ]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>


@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 1&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Enable Debug &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 2&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Memory Initialization)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Stage 3&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Boot to UEFI Shell only &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 4&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 5&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS w/ Security enabled&nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 6&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Advanced Feature Selection)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 7&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Performance Opetimizations &nbsp;)</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations



---?image=assets/images/slides/Slide65.JPG
@title[Boot Flow – Stage 3]
<p align="right"><span class="gold" >@size[1.1](<b>Boot Flow – Stage 3</b>)</span><span style="font-size:0.75em;" ></span></p>


Note:

 The objective of Stage III is to enable a minimal boot path that successfully loads
the UEFI Shell. A secondary objective for Stage III is to be silicon and board agnostic. All
silicon and board specific details should be leveraged from Stages I and II. Demonstrating
the capability to load the UEFI shell does not imply that the UEFI shell is a required
component in the end product firmware. It does ensure that the platforms with a terminal
boot stage target greater than Stage II can load the UEFI shell so the system can be
analyzed and configured in the UEFI boot services environment with well-defined behavior in
a consistent manner with other Minimum Platform specification-compliant systems.

The minimal UI capability that is required is serial console. UEFI variables must be
supported with at least emulated variable behavior. UEFI variable storage to a non-volatile
media such as SPI NOR flash is acceptable if the platform requirements mandate such
support. Additional capabilities are optional and must not be assumed. These include USB
input devices, graphics devices, and other storage devices.





---?image=assets/images/slides/Slide66.JPG
@title[High Level Control Flow – Stage 3]
<p align="right"><span class="gold" >@size[1.1](<b>High Level Control Flow – Stage 3</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-60 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.85em; "><br>
Major Execution Activities
</span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" > DXE Initial Program Load (IPL) </span> </li>
  <li><span style="font-size:0.65em" > DXE Core initialization and dispatcher execution </span> </li>
  <li><span style="font-size:0.65em" > Initialize the generic infrastructure required for the DXE environment </span> </li>
  <ul style="list-style-type:none; line-height:0.6;">  
      <li><span style="font-size:0.6em" > -  DXE architectural protocols - Initialization of architecturally required hardware such as timers</span> </li>
  </ul>  
  <li><span style="font-size:0.65em" > Post-memory silicon policy initialization </span> </li>
  <li><span style="font-size:0.65em" > Serial console input and output capabilities</span> </li>
</ul>
@snapend

Note:

Stage III extends Stage II control flow by executing Driver Execution Environment (DXE),
executing Boot Device Selection (BDS) and invoking the UEFI Shell.

After memory is installed during Stage II, the remaining silicon and platform initialization
must take place in the PEI phase only. All silicon initialization tasks should have been
completed in Stage II, and there should be no silicon-specific initialization required in the
DXE phase. The default console information should be transferred via a HOB and initialized
and used in Stage III.

- Universally usable infrastructure: DXE Core, Minimal BDS, console infrastructure
- Silicon agnostic architectural protocol producing hardware modules
- UEFI Variable support (emulation allowed)
- UEFI Shell
- Tests for Memory Map, Cache Map, architectural hardware




---
@title[Stage 3 Firmware Volumes]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 3 Firmware Volumes</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Name&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Content</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvUefiBoot&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" >Common UEFI, DXE & BDS Services&nbsp;</span></p></td>
	</tr>
</table>
<br>
@snapend



@snap[north-west span-100 fragment]
<br>
<br>
<br>
<br>
<br>
<p align="right"><span class="gold" >@size[1.1](<b> Stage 3 FVs Contents</b>)</span><span style="font-size:0.75em;" ></span></p>

<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>FV&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Components</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Purpose</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >FvUefiBoot&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >DxeCore.efi&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".020%" width="70%"><p style="line-height:022%"><span style="font-size:0.45em" >UEFI Sytem table, DXE Services, Dispatcher & APs		&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > . . .  &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.45em" >All other UEFI / DXE Modules, See .FDF file</span></p></td>
	</tr>
</table>	
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Mapped according to .FDF file layout<br><br>&nbsp;</span></p>)
@snapend


Note:

Stage III finalizes silicon and prepares DXE/BDS services
See 

https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/5_stage_3_boot_to_uefi_shell/52_firmware_volumes.html#52-firmware-volumes

for a list of more Modules in the FV for stage 3



---
@title[Stage 3 Platform Libraries - PEI]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 3 Platform Architecture Libraries</b>)</span><span style="font-size:0.75em;" ></b></span></p>


@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.75em;">
Stage 3 Modules - @size[.8em](List of UEFI and DXE Components: <a href="https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/content/appendix_a_full_maps/a1_firmware_volume_layout.html">EDK II Open Platform Spec.</a>)
<br>
<br>
<br>
<br>
Stage 3 Platform Architecture Libraries
</span></p>


<table id="recTable-1">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Item</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:30%"><span style="font-size:0.5em" ><b>API Definition</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:30%"><span style="font-size:0.5em" ><b>Producing Pkg</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Description</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > SerialPortLib </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MdeModulePkg </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg </span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:01%"><span style="font-size:0.4em" >  Serial port leveraging PEI and HOB initializatio </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > PlatformBootManagerLib </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MdeModulePkg </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > MinPlatformPkg </span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:01%"><span style="font-size:0.4em" >  Basic platform boot manager port. </span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south span-95 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Only modules in the board package should be modified <br><br>&nbsp;</span></p>)
@snapend


Note:



Only modules in the board package should be modified in the process of board porting. The minimum platform package and other common package 
contents must not be directly modified. The board package and silicon package modules may have multiple instances to support different boards and different silicon. 
These components are required. They enable orderly board porting and add the support for extensibility in later stages. The libraries consumed are the subset of 
libraries required by this specification. 

See:
https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/5_stage_3_boot_to_uefi_shell/53_modules.html#53-modules


To find the Libraries for the Platform specific code
1 Search the Work space .DSC files for the string of the library
2 Open the .DSC files associated with the platform
3 Determine which Library is used and that should have the build path in the workspace.


For KabyLake only the PlatformBootManagerLib will be ported.
Serial port is standard EDK II from MdeModulePkg/Library/BaseSerialPortLib16550



---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules - Stage 3 PEI]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules</b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:45%" align="left" ><span style="font-size:0.75em;">Silicon Initilization done in Stage 2 for Stage 3</span></p>

@snap[north-west span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
 Include/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[yellow](BoardinitLib.h)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[yellow](SiliconPolicyInitLib.h)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[yellow](SiliconPolicyUpdateLib.h)  <br>&nbsp;&nbsp;
 <br>&nbsp;&nbsp;
 Library/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  . . . <br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformInitPostMem/ 
</span></p>
@snapend

@snap[north-east span-45 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
BoardInitBeforeSiliconInit() <br>
 <br>
SiliconPolicyInitPostemory() <br>
SiliconPolicyUpdatePostMemory() <br>
SiliconPolicyDonePostMemory() <br>
 <br>
BoardInitAfterSiliconInit() <br>
 <br>
DxeLoadCore()
</span></p>

@snapend



@snap[south-east span-48 fragment]
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" > No silicon-specific initialization in DXE phase </span> </li>
  <li><span style="font-size:0.65em" > HOBs should transfer Init settings to Stage 3</span> </li>
</ul>
<br>
<br>
<br>
@snapend


Note:


The following functions on Right are required to exist and to execute in the listed order. The
component that provides the function is not specified because it is not required by the
architecture.

After memory is installed during Stage II, the remaining silicon and platform initialization
must take place in the PEI phase only. All silicon initialization tasks should have been
completed in Stage II, and there should be no silicon-specific initialization required in the
DXE phase. The default console information should be transferred via a HOB and initialized
and used in Stage III.




---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules - Stage 3 DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules</b>)</span><span style="font-size:0.75em;" ><br>- Stage 3 DXE</span></p>

@snap[north-west span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-49 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
 Include/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
   @color[yellow](BoardinitLib.h)  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

 <br>&nbsp;&nbsp;
 Library/ <br>&nbsp;&nbsp;&nbsp;&nbsp;
  . . . <br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInit/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformInitPostMem/ 
</span></p>
@snapend

@snap[north-east span-45 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.5em; font-family:Consolas;"><br>
BoardNotificationInit() <br>
 <br>
</span></p>

@snapend



@snap[south-east span-48 fragment]
<p style="line-height:70%" align="left" ><span style="font-size:0.75em" >
Create Events:<br>
&bull; &nbsp;&nbsp; PCI Enumeration complete<br>
&bull; &nbsp;&nbsp; DXE SMM ready to Lock
</span></p>
<br>
<br>
<br>
<br>
<br>
@snapend


Note:

BoardInitLib BoardNotificationInit Platform Board specific initialization hook
at DXE phase



---?image=assets/images/slides/Slide71.JPG
@title[Initial Program Load (IPL) PEIM for DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Initial Program Load (IPL) PEIM for DXE</b>)</span><span style="font-size:0.75em;" ></span></p>
<br>
<div class="left">
<span style="font-size:0.8em" > &nbsp;</span>
</div>
<div class="right">
<br>
@ul[no-bullet]
-  <font color="white">&nbsp;&nbsp;<b><font face="Consolas">DxeLoadCore&lpar;&rpar;</font> </b></font>  <BR><br>
-  <font color="#FFFF00">&nbsp;&nbsp;<b>Creates HOBs </b></font> <br><br>
-  <font color="white">&nbsp;&nbsp;<b>Locates DXE main </b></font>  <BR><br>
-  <font color="#ffc000">&nbsp;&nbsp;<b>Switch Stacks</b></font>  <br><br>
-  <font color="cyan">&nbsp;&nbsp;<b>&rarr;&nbsp;<font face="Consolas">DxeMain&lpar;&rpar;</font></b></font> 
@ulend
</div>			


Note:
-  The DXE IPL PEIM should not require porting, but  knowing what is does it important.  This is a good place for a breakpoint and starting to debug.  For example, if porting didn’t work this is where it will fail.

-  The DXE IPL PEIM performs several tasks

  -  Shadows DXE IPL into permanent memory to allow sharing of the decompression algorithm and several other library routines (e.g. security)
  -  Allocates 128KB of stack for the DXE phase
  -  Creates HOBs for passing library routines and the firmware volumes discovered during the PEI phase. Most commonly this is the main FV and any other FVs that DXE will use to load drivers from (for example backup block)
  -  If S3, then the OS waking vector is called
  -  Locate DXE Main in the FVs
  -  If not S3 then switch stacks and call DXE Main


Characteristics 
-  The last PEIM to execute
-  Shadows into permanent memory
-  Shares data from PEI phase with DXE
-  Creates a stack for DXE Phase
-  Creates HOBs
-  Calls S3 vector if appropriate
-  Locate DXE Main
-  Switch stack and call DXE Main





---?image=assets/images/slides/Slide72.JPG
@title[DXE Phase Stage 3]
<p align="right"><span class="gold" >@size[1.1](<b>DXE Phase Stage 3</b>)</span><span style="font-size:0.75em;" ></span></p>

<div class="left-1">
<span style="font-size:0.8em" > &nbsp;</span>
</div>
<div class="right-1">
<br>
<br>
<ul style="list-style-type:none; line-height:0.8;">
  <li><span style="font-size:0.9em" ><font color="yellow">DXE Core initialization and dispatcher execution </font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="cyan">Establish Architectural Protocols </font> </span></li><br>
  <li><span style="font-size:0.9em" ><font color="#ffc000">Install any required DXE / UEFI Drivers for Stage 3 </font> </span></li>
</ul>
</div>		

Note:


Again, the DXE Main core code should not require porting, but  knowing what is does it important.

-  The main platform DXE code is in subdirectories of the platform package having “DXE” in the directory name (i.e. PciPlatformDxe)
   -  It will reference other packages DXE modules
-  Establish the architectural protocols
  -  Isolate platform specific hardware (e.g., RTC)
  -  Provide support for boot and runtime services
  -  Low level protocols that support DXE APIs
  -  Directly called by DXE core
-  Install any required DXE and then the UEFI Drivers


---?image=assets/images/slides/Slide73.JPG
@title[Architectural Protocols for KabyLake]
<p align="right"><span class="gold" >@size[1.1](<b>Architectural Protocols for KabyLake</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:


Silicon agnostic architectural protocol producing hardware modules

Example show KabyLake APs

For the gEfiTimerArchProtocolGuid 

Search the workspace for all .inf files with the string: gEfiTimerArchProtocolGuid 
Notice there are 2 where this protocol is gEfiTimerArchProtocolGuid                     ## PRODUCES
Next search the board/platform .dsc file for which .inf file is included.

We find that  PcAtChipsetPkg\HpetTimerDxe/HpetTimerDxe.inf is included in the platform .dsc file


- gEfiBdsArchProtocolGuid 	`MdeModulePkg/Universal/BdsDxe/ `
- gEfiCapsuleArchProtocolGuid 	`MdeModulePkg/Universal/CapsuleRuntimeDxe `
- gEfiCpuArchProtocolGuid                       	`UefiCpuPkg/CpuDxe/`
- gEfiMetronomeArchProtocolGuid 	`MdeModulePkg/Universal/Metronome`
- gEfiMonotonicCounterArchProtocolGuid 	`MdeModulePkg/Universal/MonotonicCounterRuntimeDxe `
- gEfiRealTimeClockArchProtocolGuid 	`PcAtChipsetPkg/PcatRealTimeClockRuntimeDxe`
- gEfiResetArchProtocolGuid 	`MdeModulePkg/Universal/ResetSystemRuntimeDxe`
- gEfiRuntimeArchProtocolGuid 	`MdeModulePkg/Core/RuntimeDxe `
- gEfiSecurity2ArchProtocolGuid 	`MdeModulePkg/Universal/SecurityStubDxe`
- gEfiStatusCodeRuntimeProtocolGuid 	`MdeModulePkg/Universal/ReportStatusCodeRouter/RuntimeDxe` 
- gEfiTimerArchProtocolGuid 	`PcAtChipsetPkg/HpetTimerDxe`
- gEfiVariableArchProtocolGuid 	`MdeModulePkg/Universal/Variable/RuntimeDxe/VariableRuntimeDxe` or        `VariableSmmRuntimeDxe` (depends on PcdBootToShellOnly)

- gEfiVariableWriteArchProtocolGuid 	`MdeModulePkg/Universal/Variable/RuntimeDxe/VariableRuntimeDxe` or   `VariableSmmRuntimeDxe` (depends on PcdBootToShellOnly)

- gEfiWatchdogTimerArchProtocolGuid 	`MdeModulePkg/Universal/WatchdogTimerDxe `




---?image=assets/images/slides/Slide37.JPG
@title[Platform Initialization Board Hook Modules - Stage 3 DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board Hook Modules</b>)</span><span style="font-size:0.75em;" ><br>- Stage 3 DXE - BDS</span></p>

@snap[north-west span-52 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-47 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
 Bds/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      DxePlatformBootManagerLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         BdsPlatform/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
           @color[yellow](PlatformBootManagerBeforeConsole&lpar;&rpar;)
</span></p>
@snapend

@snap[north-east span-44 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.65em; font-family:Consolas;"><br><br>
PlatformBootManagerLib <br>
 <br>
</span></p>

@snapend



@snap[south-east span-95 ]
<p style="line-height:80%" align="left" ><span style="font-size:0.8em" >
&bull; &nbsp;&nbsp;Call before BDS to connect all devices<br>
&bull; &nbsp;&nbsp;Creates event,<font face="Consolas">@size[.8em](OnReadyToBootCallBack)</font><br>
&bull; &nbsp;&nbsp;Updates consule etc.<br>
</span></p>
<br>
<br>
@snapend



@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Typically, no board porting is required<br><br>&nbsp;</span></p>)
@snapend


Note:

To find the Libraries for the Platform specific code
1 Search the Work space .DSC files for the string of the library
2 Open the .DSC files associated with the platform
3 Determine which Library is used and that should have the build path in the workspace.

- Call before BDS to connect all devices
- Creates event, OnReadyToBootCallBack
- Updates consule etc.


- No board porting of these libraries is required.



---
@title[Stage 3 Checklist  ]
<p align="center"><span class="gold" >@size[1.1](<b>Stage 3 Checklist</b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; ">
Steps to enable a board for Stage 3.
</span></p>

@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

@snap[north-west span-100 ]
<br>
<br>
<br>
<ul style="list-style-type:None; line-height:0.7;">
 <li><span style="font-size:0.65em" >1.&nbsp;&nbsp; Add board post-memory initialization code in 
 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font face="Consolas">@size[.7em](BoardInitBeforeSiliconInit &lpar;&rpar;)</font> and <font face="Consolas">@size[.7em](BoardInitAfterSiliconInit &lpar;&rpar;)</font> ,
 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font face="Consolas">@size[.7em](BoardPkg/BoardInitLib/PeiBoardXxxInitPostMemoryLib.c)</font></span> </li>
  <ul style="list-style-type:none; line-height:0.5;">
     <li><span style="font-size:0.5em" >&bull; &nbsp;&nbsp; Initialize board-specific hardware device, such as GPIO.</span><li>
     <li><span style="font-size:0.5em" >&bull; &nbsp;&nbsp; Update post-memory policy configuration by using PCD.</span><li>
  </ul> 
 <li><span style="font-size:0.65em" >2.&nbsp;&nbsp; Add board policy update code in <font face="Consolas">@size[.8em](SiliconPolicyUpdatePostMemory &lpar;&rpar;)</font> ,
<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font face="Consolas">@size[.7em](BoardPkg\PeiSiliconPolicyUpdateLib \PeiBoardXxxInitLib.c.)</font></span> </li>
  <ul style="list-style-type:none; line-height:0.5;">
     <li><span style="font-size:0.5em" >&bull; &nbsp;&nbsp; The PCD updated in <font face="Consolas">@size[.9em](BoardInitBeforeSiliconInit &lpar;&rpar;)</font> might be used here.</span><li>
  </ul> 
 <li><span style="font-size:0.65em" >3.&nbsp;&nbsp;  Add board initialization DXE code in <font face="Consolas">@size[.7em](BoardInitAfterPciEnumeration &lpar;&rpar;)</font>,
 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <font face="Consolas">@size[.8em](BoardInitReadyToBoot&lpar;&rpar;,   BoardInitEndOfFirmware &lpar;&rpar;)</font> . </span> </li>
   <ul style="list-style-type:none; line-height:0.5;">
     <li><span style="font-size:0.5em" >– Note: The functions may be empty if no updating is required.</span> </li>
   </ul>
 <li><span style="font-size:0.65em" >4.&nbsp;&nbsp;  Ensure all PCDs in the configuration section (DSC files) are correct for your 
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;board. -  Set <font face="Consolas">@size[.8em](gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 3)</font></span> </li>
 <li><span style="font-size:0.65em" >5.&nbsp;&nbsp;  Ensure all required binaries in the flash file (FDF files) are correct for your 
  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;board.</span> </li>
 <li><span style="font-size:0.65em" >6.&nbsp;&nbsp;  Boot, collect debug log, and verify the test point results are correct.</span> </li>
</ul>

<p style="line-height:70%" align="left" ><span style="font-size:0.45em; ">
<a href="https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/5_stage_3_boot_to_uefi_shell/59_test_point_results.html">EDK II Open Platform Spec Test points Stage 3</a>
</span></p>

@snapend


Note:

Steps to enable a board for Stage III
Add board post-memory initialization code in BoardInitBeforeSiliconInit () and
BoardInitAfterSiliconInit () ,
BoardPkg/BoardInitLib/PeiBoardXXXInitPostMemoryLib.c.
i. Initialize board-specific hardware device, such as GPIO.
ii. Update post-memory policy configuration by using PCD.
2. Add board policy update code in SiliconPolicyUpdatePostMemory () ,
BoardPkg\PeiSiliconPolicyUpdateLib \PeiBoardXXXInitLib.c.
i. The PCD updated in BoardInitBeforeSiliconInit () might be used here.
3. Add board initialization DXE code in BoardInitAfterPciEnumeration () ,
BoardInitReadyToBoot () , BoardInitEndOfFirmware () .
i. NOTE: The functions may be empty if nothing needs to be updated.
4. Ensure all PCDs in the configuration section (DSC files) are correct for your board.
i. Set gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 2
5. Ensure all required binaries in the flash file (FDF files) are correct for your board.
6. Boot, collect debug log, and verify the test point results defined in section 5.9 of the EDK II Open platform spec are
correct.
 

EDK II Open platform spec Test points Stage 3: 
https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/5_stage_3_boot_to_uefi_shell/59_test_point_results.html


---?image=assets/images/slides/Slide_TableDHote.JPG
@title[Staged Approach by Features Section 04 ]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>


@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 1&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Enable Debug &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 2&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Memory Initialization)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 3&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot to UEFI Shell only &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Stage 4&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Boot ot OS)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 5&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS w/ Security enabled&nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 6&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Advanced Feature Selection)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 7&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Performance Opetimizations &nbsp;)</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations



---?image=assets/images/slides/Slide77.JPG
@title[Boot Flow – Stage 4]
<p align="right"><span class="gold" >@size[1.1](<b>Boot Flow – Stage 4</b>)</span><span style="font-size:0.75em;" ></span></p>


Note:

The objective of Stage IV is to enable a minimal boot path that successfully boots a
commercial operating system such as Linux or Windows, with UEFI interfaces exposed to
the OS implemented in compliance with the UEFI specification. The minimal boot path only
involves functionality necessary to load the OS to a state where a user may begin
performing more complex interactions. This involves successfully reaching an environment
that allows the user to launch applications. 


The stage does not include support for all
applications that, for example, may require certain CPU or GPU features enabled. Nor does
it require any further support, including but not limited to device and system power
management, full hardware performance support enabled, system reset support, etc.
Any additional functionality is classified as an advanced feature. Those features are
collectively enabled in Stage VI.






---?image=assets/images/slides/Slide78.JPG
@title[High Level Control Flow – Stage 4]
<p align="right"><span class="gold" >@size[1.1](<b>High Level Control Flow – Stage 4</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-57 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.85em; "><br>
Major Execution Activities
</span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" > Minimum ACPI Table Initialization </span> </li>
  <li><span style="font-size:0.65em" > Additional input, output, and storage support based on platform and operating system requirements</span> </li>
  <li><span style="font-size:0.65em" > SMM </span> </li>
  <li><span style="font-size:0.65em" > Perform ACPI enable/disable</span> </li>
  <li><span style="font-size:0.65em" > Kernel debug support</span> </li>
  <li><span style="font-size:0.65em" > UEFI variable support</span> </li>
</ul>
@snapend

Note:


Stage IV introduces additional functionality to meet the minimal requirements for a UEFIcompliant
operating system. Much of the support required will be performed during the DXE
phase interleaving Stage IV control flows with pre-existing control flows from Stage III. A
minimum set of ACPI tables, namely RSDT, FACP, FACS, FADT, MADT, HPET and DSDT,
need to be initialized and published. If there are alternative and/or additional operating
system expectations such as full DeviceTree support, that should be enabled to allow the
operating system to be loaded.


It is recommended that only the mandatory boot option devices are connected in BDS to
minimize complexity and boot time in the minimal execution path to the operating system. In
the flow diagram below, the left half is identical to the functionality enabled by Stage III prior
to entering the BDS phase. It is expected that the Stage III components are reused to
complete Stage IV tasks.


The green blocks on slide Control Flow are reuse of the existing blocks from Stage III




---
@title[Stage 4 Firmware Volumes]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 4 Firmware Volumes</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Name&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Content</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > FvOsBoot&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > Continued DXE/BDS Services&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > FvLateSilicon&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > ACPI and SMM silicon support&nbsp;</span></p></td>
	</tr>
</table>
<br>
<ul style="list-style-type:none; line-height:0.7;">
  <li><span style="font-size:0.75em" >&bull;&nbsp;&nbsp; Finalize silicon initialization</span> </li>
  <li><span style="font-size:0.75em" >&bull;&nbsp;&nbsp; Add basic operating system required interfaces</span> </li>
  <li><span style="font-size:0.75em" >&bull;&nbsp;&nbsp; Add support for minimal featured operating system boot. </span> </li>
</ul>

@snapend




Note:

Stage IV finalizes silicon initialization, adds basic operating system required interfaces, and
supports minimally featured operating system boot. The new components are support in a
dedicated firmware volume.



---
@title[Stage 4 Firmware Volumes Contents]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 4 FVs Contents</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>

<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>FV&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Components</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Purpose</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > FvOsBoot&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" > FvLateSilicon.fv&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="70%"><p style="line-height:022%"><span style="font-size:0.45em" > Additional silicon initialization support that is performed late in boot&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; " > List of ACPI modules&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="70%"><p style="line-height:022%"><span style="font-size:0.45em" > ACPI Table, Platform & Board DXE &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; " >List of SMM modules &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="70%"><p style="line-height:022%"><span style="font-size:0.45em" > SmmIpl, SMM Core,SMM CPU etc, (DXE) &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:21%"><span style="font-size:0.4em; " > List Storage media modules&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="70%"><p style="line-height:.02%"><span style="font-size:0.45em" > Sata, USB, . . . , (DXE)&nbsp;</span></p></td>
	</tr>
</table>	
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Mapped according to .FDF file layout<br><br>&nbsp;</span></p>)
@snapend


Note:

1.  Late silicon - Additional silicon initialization support that is performed late in the boot
2. ACPI Modules - Acpi Table, platform & Board Dxe 
3. SMM Modules - SmmIpl, SMM Core,SMM CPU etc, DXE 
4. Storage Media - Sata, USB, Bus etc, DXE

https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/6_stage_4_boot_to_os/62_firmware_volumes.html#62-firmware-volumes

for a list of more Modules in the FV for stage 


---
@title[Stage 4 Platform Libraries - PEI]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 4 Platform Architecture Libraries</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.75em;">
Stage 4 Modules - @size[.8em](List of UEFI and DXE Components: <a href="https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/content/appendix_a_full_maps/a1_firmware_volume_layout.html">EDK II Open Platform Spec.</a>)
<br>
<br>
<br>
Stage 4 Platform Architecture Libraries
</span></p>


<table id="recTable-1">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Item</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:30%"><span style="font-size:0.5em" ><b>API Definition</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:30%"><span style="font-size:0.5em" ><b>Producing Pkg</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.5em" ><b>Description</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  BoardAcpiLib</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  MinPlatformPkg</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  BoardPkg</span></p></td>
		<td bgcolor="#121212" height=".02%" width="50%"><p style="line-height:01%"><span style="font-size:0.4em" >   Services for ACPI table creation and SMM enable/dis</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  BoardInitLib</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  MinPlatformPkg</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.4em; font-family:Consolas;" >  BoardPkg</span></p></td>
		<td bgcolor="#121212" height=".02%" width="50%"><p style="line-height:21%"><span style="font-size:0.4em" >Board specific initialization hook at DXE phase for BoardNotificationInit   </span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south span-95 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em">Board porting requires creation of libraries produced <br>by the <font face="Consolas">@size[.85em](BoardPkg)</font> <br>&nbsp;</span></p>)
@snapend


Note:

To find the Libraries for the Platform specific code
1 Search the Work space .DSC files for the string of the library
2 Open the .DSC files associated with the platform
3 Determine which Library is used and that should have the build path in the workspace.

Board porting will require creation of libraries identified as produced by the BoardPkg.


Depending on the board, there may be existing libraries that are sufficient for a board, so it is
important to assess the utility of existing library instances when developing board support.



---
@title[Tips for Board Specific ACPI  ]
<p align="right"><span class="gold" >@size[1.1](<b> Tips for Board Specific ACPI </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-70 ]
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-31 ]
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><b>Board Library</b><br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b> NVS Space</b><br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b> Special Features</b><br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:80%"><span style="font-size:0.9em;" ><b> ASL & C In<br> Same  Dir </b><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-68 ]
<br>
<br>
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Use board specific library for ACPI global NVS area<br>&nbsp;&nbsp; assignments instead defining in ASL Code<br><br></span></p>)
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Do Not define huge amount of board specific<br>&nbsp;&nbsp; configuration in the global NVS area<br><br><br></span></p>)
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Board specific devices or advanced features<br>&nbsp;&nbsp;  should be moved to the board specific directory<br><br></span></p>)
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Use the same directory for the <font face="Consolas">@size[.7em](GlobalNvs.asl)</font><br>&nbsp;&nbsp; and <font face="Consolas">@size[.7em](GobalNvsAreaDef.h)</font>  files<br><br><br></span></p>)
@snapend


Note:

It is not recommended define BoardId in ACPI global NVS and use the board ID check in the ASL code. Use a board specific library instead

Do Not define huge amount of board specific configuration in the global NVS area because a generic platform should not have the board specific knowledge 

If this Global NVS is for a board specific device, it should be moved to the board specific directory. A board should define a board specific NVS, or just use a simple Name object under this device node. 

If this Global NVS is for a board advanced feature, it should be moved to the feature directory. This fetaure driver should define a feature specific NVS, or just use a simple Name object for the feature. 


The Global NVS ASL definition (such as https://github.com/tianocore/edk2-platforms/blob/devel-MinPlatform/Platform/Intel/KabylakeOpenBoardPkg/Include/Acpi/GlobalNvs.asl) and C-language definition (such as https://github.com/tianocore/edk2-platforms/blob/devel-MinPlatform/Platform/Intel/KabylakeOpenBoardPkg/Include/Acpi/GlobalNvsAreaDef.h) should be put to same directory. As such people can compare them to know the mapping between C-language definition and ASL definition. A better is to use a tool to create one from the other to avoid mismatch issue. 




---?image=assets/images/slides/Slide37.JPG
@title[Example: Board Specific ACPI ]
<p align="right"><span class="gold" >@size[1.1](<b>Example: Board Specific ACPI </b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[south-west span-100 ]
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
<br>
@snapend

@snap[north-east span-95 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.7em" ><br><br>
&bull; &nbsp;&nbsp;Tip: Board specific device selection - define a board-neutral name<br>
&bull; &nbsp;&nbsp;Data structure is board neutral <font face="Consolas">@size[.8em](@color[yellow]( .../Include/Acpi/GlobalNvsAreaDef.h ))</font><br>
&bull; &nbsp;&nbsp;File:&nbsp; <font face="Consolas">@size[.75em](@color[yellow](KabylakeOpenBoardPkg/KabylakeRvp3/Library/BoardAcpiLib/))<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @size[.75em](@color[yellow](DxeKabylakeRvp3AcpiTableLib.c))</font>
</span></p>

@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:35%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br><br>
VOID<br>
@color[yellow](KabylakeRvp3UpdateGlobalNvs) (<br>
VOID<br>
)<br>
&lbrace; // <font face="Arial">@color[#A8ff60](Update global NVS area for ASL and SMM init code to use)</font> <br>&nbsp;&nbsp;
mGlobalNvsArea.Area = (VOID *)(UINTN)PcdGet64 (PcdAcpiGnvsAddress);<br>&nbsp;&nbsp;
mGlobalNvsArea.Area-&gt;PowerState = 1;<br>&nbsp;&nbsp;
mGlobalNvsArea.Area-&gt;NativePCIESupport = PcdGet8 (PcdPciExpNative);<br>&nbsp;&nbsp;
mGlobalNvsArea.Area-&gt;ApicEnable = GLOBAL_NVS_DEVICE_ENABLE;<br>&nbsp;&nbsp;
mGlobalNvsArea.Area-&gt;LowPowerS0Idle = PcdGet8 (PcdLowPowerS0Idle);<br>&nbsp;&nbsp;
mGlobalNvsArea.Area-&gt;Ps2MouseEnable = FALSE;<br>&nbsp;&nbsp;
mGlobalNvsArea.Area-&gt;Ps2KbMsEnable = PcdGet8 (PcdPs2KbMsEnable);<br>
&rbrace;
</span></p>
@snapend



@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Tip: use board specific library for ACPI NVS Area<br><br>&nbsp;</span></p>)
@snapend


Note:

It is not recommended define BoardId in ACPI global NVS and use the board ID check in the ASL code.

BKM is to define a board-neutral name for the branch condition  
If this device is a silicon device and it might be enabled/disabled by policy, BKM recommended is using the this mechanism. 

Protocol from 
KabylakeOpenBoardPkg\Include\Protocol\GlobalNvsArea.h

Data structure typedef:
KabylakeOpenBoardPkg\Include\Acpi\GlobalNvsAreaDef.h


The other way to resolve above issue is to move the board specific ACPI Secondary System Description Table (SSDT) to the board specific directory and let it be installed by a board specific ACPI driver. The basic platform ACPI driver should only handle generic ACPI tables, like FADT, MCFG, HPET, MCFG, and etc. 

This means the .asi  has to determine specifics
A better way is to keep those board specific SSDT in board directly using a board specific library as the example of this slide


---?image=assets/images/slides/Slide37.JPG
@title[Required Function Interfaces DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Required Function Interfaces DXE</b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[north-west span-52 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-47 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
MinPlatformPkg/ <br>&nbsp;&nbsp;
 PlatformInit/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      MultiBoardInitSupportLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         DxeMultiBoardInitSupportLib.c<br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInitDxe/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitDxe.c <br>&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;
       @color[yellow](BoardNotificationInitEntryPoint&lpar;&rpar;)
</span></p>
@snapend

@snap[north-east span-44 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.65em; font-family:Consolas;"><br><br>
@color[yellow](BoardInitLib) <br>
 <br>
</span></p>
<br><br>

<p style="line-height:70%" align="left" ><span style="font-size:0.75em" >
Board specific initialization hook at DXE phase.<br><br>
Notify:<br>
<font face="Consolas">@size[.8em](@color[yellow](OnPciEnumerationComplete ))</font><br>
<font face="Consolas">@size[.8em](@color[yellow](SmmReadyToLockRegistration))</font>
</span></p>

@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Registers two callbacks to call FSP notifies<br><br>&nbsp;</span></p>)
@snapend


Note:

This routine registers two callbacks to call fsp's notifies


---?image=assets/images/slides/Slide37.JPG
@title[Required SMM Function Interfaces DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Required SMM Function Interfaces DXE</b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[north-west span-52 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-47 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
KabylakeOpenBoardPkg/ <br>&nbsp;&nbsp;
 KabylakeRvp3/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      BoardAcpiLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](SmmBoardAcpiEnableLib.c)<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
		 or<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](SmmMultiBoardAcpiSupportLib.c)<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-44 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.65em; font-family:Consolas;"><br><br>
@color[yellow](BoardAcpiEnableLib) <br>
 <br>
</span></p>
<br><br>

<p style="line-height:70%" align="left" ><span style="font-size:0.75em" >
Board specific initialization hook at DXE phase.<br><br>
<br>
<font face="Consolas">@size[.8em](@color[yellow](SiliconEnableAcpi &lpar;&rpar; ))</font><br>
<font face="Consolas">@size[.8em](@color[yellow](SiliconDisableAcpi &lpar;&rpar;))</font>
</span></p>

@snapend


Note:

This routine registers two callbacks to call fsp's notifies


---?image=assets/images/slides/Slide37.JPG
@title[Required SMM Function Interfaces DXE]
<p align="right"><span class="gold" >@size[1.1](<b>Required SMM Function Interfaces DXE</b>)</span><span style="font-size:0.75em;" ></span></p>

@snap[north-west span-52 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-47 ]
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-98 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.45em; font-family:Consolas;"><br>
Platform/Intel/<br>
KabylakeOpenBoardPkg/ <br>&nbsp;&nbsp;
 KabylakeRvp3/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      BoardAcpiLib/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](DxeBoardAcpiTableLib.c)<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
		 or<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
         @color[yellow](DxeMultiBoardAcpiSupportLib.c)<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-44 ]
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.65em; font-family:Consolas;"><br><br>
@color[yellow](BoardAcpiTableLib) <br>
 <br>
</span></p>
<br><br>

<p style="line-height:70%" align="left" ><span style="font-size:0.75em" >
Board specific initialization hook at DXE phase.<br><br>
<br>
<font face="Consolas">@size[.8em](@color[yellow](BoardUpdateAcpiTable&lpar;&rpar; ))</font><br>
</span></p>

@snapend


Note:

This routine registers two callbacks to call fsp's notifies



---
@title[Stage 4 Checklist  ]
<p align="center"><span class="gold" >@size[1.1](<b>Stage 4 Checklist</b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em; "><br>
Steps to enable a board for Stage 4.
</span></p>

@snap[north-east span-13]
![Porting_task_list.gif](/assets/images/tenor.gif)
@snapend

@snap[north-west span-100 ]
<br>
<br>
<br>
<br>
<ul style="list-style-type:None; line-height:0.75;">
 <li><span style="font-size:0.78em" >1.&nbsp;&nbsp; Install the minimal DSDT <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;&nbsp; In rare cases: Install board-specific SSDT </span></li>
 <li><span style="font-size:0.78em" >2.&nbsp;&nbsp; Ensure all PCDs in the configuration section (DSC files) are<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  correct for your board. <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;&nbsp; Set <font face="Consolas">@size[.8em](gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 4)</font></span></li>
 <li><span style="font-size:0.78em" >3.&nbsp;&nbsp; Ensure all required binaries in the flash file (FDF files) are<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; correct for your board.</span></li>
 <li><span style="font-size:0.78em" >4.&nbsp;&nbsp; Boot, collect log, verify test point results defined are correct</span></li>
</ul>
<br>
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.45em; ">
<a href="https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/6_stage_4_boot_to_os/69_test_point_results.html">EDK II Open Platform Spec Test points Stage 4</a>
</span></p>

@snapend


Note:


Steps to enable a board for Stage IV
1. Install the minimal DSDT - In rare cases: Install board-specific SSDT
2. Ensure all PCDs in the configuration section (DSC files) are correct for your board. - Set gMinPlatformPkgTokenSpaceGuid.PcdBootStage = 4
3. Ensure all required binaries in the flash file (FDF files) are correct for your board.
4. Boot, collect log, verify test point results defined in section 6.9 Test Point Results are
correct



EDK II Open Platform Spec Test points Stage 4:

https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/6_stage_4_boot_to_os/69_test_point_results.html




---?image=assets/images/slides/Slide_TableDHote.JPG
@title[Staged Approach by Features Section 05 ]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>


@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 1&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Enable Debug &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 2&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Memory Initialization)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 3&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot to UEFI Shell only &nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 4&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Boot ot OS)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Stage 5&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[yellow](Boot ot OS w/ Security enabled&nbsp;)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 6&nbsp;)</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Advanced Feature Selection)</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Stage 7&nbsp;)</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >@color[#808080](Performance Opetimizations &nbsp;)</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations



---?image=assets/images/slides/Slide89.JPG
@title[Boot Flow – Stage 5]
<p align="right"><span class="gold" >@size[1.1](<b>Boot Flow – Stage 5</b>)</span><span style="font-size:0.75em;" ></span></p>


Note:

The objective of Stage V is to establish the basic system security foundation for a production
environment. Given the importance of security for all connected systems, the platform
architecture considers the following basic security features as minimum requirements for any
product and thus an important part of the effort to produce a minimal platform. This stage is
concerned with enabling security technologies described in industry specifications. Lowerlevel
chipset-specific security technologies such as register locks may exist and those
should be enabled during standard silicon initialization flows in earlier stages.



---?image=assets/images/slides/Slide90.JPG
@title[Stage 5 is Focused on Security ]
<p align="right"><span class="gold" >@size[1.1](<b>Stage 5 is Focused on Security </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" >
List of Documents on Security with EDK II -     <a href="https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Security-White-Papers">EDK II tianocore Wiki </a><br><br>
Minimal security checks should be done
</span></p>
@snapend

@snap[north-west span-70]
<br>
<br>
<p style="line-height:40%" align="left" ><span style="font-size:0.75em;" ><br><br><br><br>
</span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" ><a href="https://github.com/chipsec/chipsec">Chipsec</a> </span> </li>
  <li><span style="font-size:0.65em" > Microsoft Hardware Security Test Interface (HSTI)</span> </li>
  <li><span style="font-size:0.65em" > Windows Security Mitigations Table (WSMT). </span> </li>
  <li><span style="font-size:0.65em" > Memory Attribute Table </span> </li>
  <li><span style="font-size:0.65em" > SMM Memory Attribute Table </span> </li>
  <li><span style="font-size:0.65em" > 3rd party option ROM </span> </li>
  <li><span style="font-size:0.65em" > Trusted Console - Trusted Storage </span> </li>
  <li><span style="font-size:0.65em" > DMA protection for VT-d/IOMM</span> </li>
  <li><span style="font-size:0.65em" > SMI Handler</span> </li>
  <li><span style="font-size:0.65em" > TPM</span> </li>
  <li><span style="font-size:0.65em" > Firmware Update</span> </li>
</ul>
<br>
<br>
@snapend


Note:


Once the board porting work is finished, some minimal security checks should be done to make sure there is not security hole



---
@title[Stage 5 Porting - Goals]
<p align="right"><span class="gold" >@size[1.1](<b>Stage 5 Porting - Goals</b>)</span><span style="font-size:0.75em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" >
Satisfy industry standard security specifications 
</span></p>

@snap[north-west span-85 ]
<br>
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" ><span style="font-size:0.75em;" >&nbsp;&nbsp;Establish a Static Root of Trust for Verification (S-RTV)  <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" ><span style="font-size:0.75em;" >&nbsp;&nbsp;Static Root of Trust for Measurement (S-RTM) <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" ><span style="font-size:0.75em;" >&nbsp;&nbsp;Direct Memory Access (DMA) Protection  <br>&nbsp;</span></p>)
@snapend


Note:

Stage V introduces new modules and requirements to the boot incrementally over Stage IV.

The key requirement is to satisfy industry standard security specifications applicable to the
platform. The security technologies enabled in this stage are not strictly bound to the
definition in this specification and may consist of a subset or superset of the content
described in this section. However, the only case in which a modern production system
should not implement a form of any of these technologies is if the necessary hardware is not
available. In all other cases, the system must at least implement a form of the following

Goals -
-  Hardware rooted authenticated boot that can establish a Static Root of Trust for Verification (S-RTV) and continue an authenticated chain of verification throughout the boot process.
-  System measurement capability that allows the firmware to serve as a Static Root of Trust for Measurement (S-RTM).
-  Protection from Direct Memory Access (DMA) attacks.



---
@title[Stage 5 – Security- Features ]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 5 – Security- Features </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-70  ]
<br>
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-31 fragment ]
<br>
<br>
<br>
@box[bg-green-pp text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><b><br>TCG trusted boot</b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-68 fragment]
<br>
<br>
<br>
@css[text-white ](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >TCG measured boot chain of trust should be enabled in this stage.<br><br><br></span></p>)
@snapend


@snap[north-west span-31 fragment]
<br>
<br>
<br>
@box[bg-green-pp text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><b><br>TCG trusted boot</b><br><br>&nbsp;</span></p>)
@box[bg-green-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b><br> UEFI Secure Boot</b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-68 fragment]
<br>
<br>
<br>
@css[text-white ](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >TCG measured boot chain of trust should be enabled in this stage.<br><br><br></span></p>)
@css[text-white ](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >Authenticated UEFI Variable support must be completely functional. This is a basic requirement for secure authentication and UEFI Secure Boot key management<br><br><br></span></p>)
@snapend


Note:

The TCG measured boot chain of trust should be enabled in this stage. 


At this point,
Authenticated UEFI Variable support must be completely functional. This is a basic
requirement for secure authentication and management of the UEFI Secure Boot keys.



---
@title[Stage 5 Firmware Volumes]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 5 Firmware Volumes</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Name&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:10%"><span style="font-size:0.65em" ><b>Content</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >  FvSecurity&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > Security related modules&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;&nbsp;  FvSecurityPreMemory&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;&nbsp;  FvSecurityPostMemory&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >&nbsp;&nbsp;&nbsp;  FvSecurityLate&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" >  NvStorage&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em" > Real NV storage on flash&nbsp;</span></p></td>
	</tr>
</table>
<br>

<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >
Supports key security features
</span></p>


@snapend




Note:

Stage V supports key secutiy features.



---
@title[Stage 5 Firmware Volumes Contents]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 5 FVs Contents</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<br>
<br>

<table id="recTable">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:.10%"><span style="font-size:0.65em" ><b>FV&nbsp;</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:.10%"><span style="font-size:0.65em" ><b>Components</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:.10%"><span style="font-size:0.65em" ><b>Purpose</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > FvSecurity&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="35%"><p style="line-height:01%"><span style="font-size:0.4em;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:022%"><span style="font-size:0.45em" >  &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="35%"><p style="line-height:01%"><span style="font-size:0.4em;" > List of TCG modules&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:022%"><span style="font-size:0.45em" >  TPM Services, Config, Platform, etc&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="35%"><p style="line-height:01%"><span style="font-size:0.4em;" > List of Intel&reg; VT-d modules&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:022%"><span style="font-size:0.45em" > IOMMU PEI & DXE Services &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="35%"><p style="line-height:01%"><span style="font-size:0.4em;" > List Security modules&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:022%"><span style="font-size:0.45em" > Provide security architecture protocol Secure boot UI config. . . &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:01%"><span style="font-size:0.5em; font-family:Consolas;" > &nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="35%"><p style="line-height:01%"><span style="font-size:0.4em;" > List of variable SMM modules&nbsp;</span></p></td>
		<td bgcolor="#121212" height=".02%" width="40%"><p style="line-height:022%"><span style="font-size:0.45em" >  Fault-tolerant, Variable,  SMM Services&nbsp;</span></p></td>
	</tr>
</table>	
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Mapped according to .FDF file layout<br><br>&nbsp;</span></p>)
@snapend


Note:

see :
https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/7_stage_5_security_enable/72_firmware_volumes.html 

for a list of more Modules in the FV for stage 

---
@title[Modules – Stage 5 ]
<p align="right"><span class="gold" >@size[1.1](<b> Modules – Stage 5 </b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-east span-70 ]
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-33 ]
<br>
<br>
@box[bg-navy text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b> PEI Components </b><br><br>&nbsp;</span></p>)
<br>
@box[bg-navy text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b> DXE Components </b><br><br>&nbsp;</span></p>)
<br>
@box[bg-navy text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b> SMM Components </b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-65 ]
<br>
<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" ><br>
&bull; &nbsp;&nbsp; Tcg2 Pei – SecurityPkg<br>
&bull; &nbsp;&nbsp; Tcg2 platform Pei – PlatformPkg<br>
&bull; &nbsp;&nbsp; Intel Vt-d PMR - SiliconPkg
<br><br><br>
</span></p>
<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >
&bull; &nbsp;&nbsp; Tcg2 DXE  – SecurityPkg<br>
&bull; &nbsp;&nbsp; Tcg2 platform Dxe – PlatformPkg<br>
&bull; &nbsp;&nbsp; SecureBootConfigDxe -SecurityPkg<br>
&bull; &nbsp;&nbsp; Intel Vt-d Dxe- SiliconPkg<br>
<br>
</span></p>
<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >
&bull; &nbsp;&nbsp; Tcg2 SMM  – SecurityPkg<br>
&bull; &nbsp;&nbsp; FaultTolerantWriteSMM<br>
&bull; &nbsp;&nbsp; VariableSMM<br>
<br><br>
</span></p>

@snapend


Note:

Only modules in the board package should be modified in the process of board porting. The
minimum platform package and other common package contents must not be directly
modified. The board package and silicon package modules may have multiple instances to
support different boards and different silicon. These components are required. They enable
orderly board porting and add the support for extensibility in later stages. The libraries
consumed are the subset of libraries required by this specification. Some libraries are
defined in this specification, some are defined in EDK II documentation.




---
@title[Stage 5 Required Functions]
<p align="right"><span class="gold" >@size[1.1](<b> Stage 5 Required Functions</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-100 ]
<p style="line-height:20%" align="left" ><span style="font-size:0.2em;" >&nbsp;
</span></P>
<table id="recTable-1">
	<tr>
		<td bgcolor="#0070C0" ><p style="line-height:.010%"><span style="font-size:0.5em" ><b>Phase</b></span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:.010%"><span style="font-size:0.5em" ><b>Name</b> &nbsp;</span></p></td>
		<td bgcolor="#0070C0" ><p style="line-height:.010%"><span style="font-size:0.5em" ><b>Purpose</b> &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > PEI </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  PeimEntryMA ()</span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >   Entry point for the TPM2 PEIM</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  &nbsp; </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  IntelVTdPmrInitialize ()&nbsp; </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >   Entry point for the VT-d PEIM&nbsp; </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  DXE&nbsp; </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  DriverEntry ()&nbsp; </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >  Entry point for the TPM2 DXE module&nbsp;  </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  &nbsp; </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" >  IntelVTdInitialize()&nbsp; </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >  Entry point for the VT-d DXE module &nbsp; </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > &nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > UserPhysicalPresent()&nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >  Indicates whether a physical user is present for UEFI secure boot &nbsp; </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > &nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:22%"><span style="font-size:0.4em; font-family:Consolas;" > ProcessTcgPp & ProcessTcgMor&nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:22%"><span style="font-size:0.4em" >   ProcessTcgPp Process the TPM physical presence (PP) request & memory overwrite request (MOR)&nbsp; </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > SMM&nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > InitializeTcgSmm ()&nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >   Entry point for the TPM2 SMM module&nbsp; </span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > &nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%"><p style="line-height:.01%"><span style="font-size:0.4em; font-family:Consolas;" > MemoryClearCallback ()&nbsp;  </span></p></td>
		<td bgcolor="#121212" height=".02%" width="60%"><p style="line-height:01%"><span style="font-size:0.4em" >   Callback function for setting the MOR variable &nbsp; </span></p></td>
	</tr>
</table>
<br>
@snapend



Note:
The following functions are required to exist and to execute in the given order. The
component that provides the function is not specified because it is not required by the
architecture.

All except ProcessTcgPp & ProcessTcgMor are in the EDK II Common open source code 




Depending on the board, there may be existing libraries that are sufficient for a board, so it is
important to assess the utility of existing library instances when developing board support.

---
@title[Security Related PCDs and Variables ]
<p align="right"><span class="gold" >@size[1.1](<b>Security Related PCDs and Variables</b>)</span><span style="font-size:0.75em;" ></span></p>
<ul style="list-style-type:disc; line-height:0.8;">
  <li><span style="font-size:0.75em" > Authenticated Variables – UEFI Secure Boot </span> </li>
  <ul style="list-style-type:disc; line-height:0.6;">
    <li><span style="font-size:0.55em; font-family:Consolas;" > PK, KEK, db and dbx </span> </li>
  </ul>

  <li><span style="font-size:0.75em" > TPM - Policy: TCG trusted boot </span> </li>
  <ul style="list-style-type:disc; line-height:0.6;">
    <li><span style="font-size:0.55em; font-family:Consolas;" > PcdTpmInstanceGuid, PcdTpm2InitializationPolicy, PcdTpm2SelfTestPolicy</span> </li>
  </ul>

  <li><span style="font-size:0.75em" > Memory Only Reset (MOR)- Policy: TCG MOR</span> </li>
  <ul style="list-style-type:disc; line-height:0.6;">
    <li><span style="font-size:0.55em; font-family:Consolas;" > PRE_MEM_SILICON_POLICY, L"MemoryOverwriteRequestControl"</span> </li>
  </ul>

  <li><span style="font-size:0.75em" > Intel® VT-d – DMA protection </span> </li>
  <ul style="list-style-type:disc; line-height:0.6;">
    <li><span style="font-size:0.55em; font-family:Consolas;" > PcdVTdPolicyPropertyMask</span> </li>
  </ul>

</ul>


Note:
https://edk2-docs.gitbooks.io/edk-ii-minimum-platform-specification/7_stage_5_security_enable/75_configuration.html#75-configuration

- Authenticated Variables – UEFI Secure Boot
  - PK, 
  - KEK, 
  - db and dbx
- TPM - Policy: TCG trusted boot
  - PcdTpmInstanceGuid, 
  - PcdTpm2InitializationPolicy, 
  - PcdTpm2SelfTestPolicy
- Memory Only Reset (MOR ) - Policy: TCG MOR
  - PRE_MEM_SILICON_POLICY, L“MemoryOverwriteRequestControl”
- Intel® VT-d – DMA protection 
   - PcdVTdPolicyPropertyMask




---
@title[Current Issues ]
<p align="right"><span class="gold" >@size[1.1](<b>Current Issues</b>)</span><br>
<span style="font-size:0.75em;" >- Open Source EDK II Platforms</span></p>


@snap[north span-80 ]
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" align="left"><span style="font-size:0.75em;" >&nbsp;&nbsp;Developers need a way to turn on and off of a feature <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" align="left"><span style="font-size:0.75em;" >&nbsp;&nbsp;Developers need a way to get the platform  <br>&nbsp;&nbsp;configuration data  <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" align="left"><span style="font-size:0.75em;" >&nbsp;&nbsp;Developers need to do porting work from an <br>&nbsp;&nbsp;existing board to a new board   <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2 fragment ](<p style="line-height:60%" align="left"><span style="font-size:0.75em;" >&nbsp;&nbsp;Developers might need to work on a different board  <br>&nbsp;</span></p>)
@snapend


Note:


---
@title[Goals]
<p align="right"><span class="gold" >@size[1.1](<b>GOALS</b>)</span><br>
<span style="font-size:0.75em;" ></span></p>


@snap[north-west span-30 ]
<br>
<br>
<br>
@box[bg-green-pp text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><b>Simple</b><br><br>&nbsp;</span></p>)
<br>
@box[bg-green-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Portable</b><br><br>&nbsp;</span></p>)
<br>
@box[bg-green-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Consistent</b><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-63 ]
<br>
<br>
<br>
@css[text-white fragment](<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Code structure should be obvious so that the firmware developer can easily turn on or turn off a significant feature<br><br></span></p>)
@css[text-white fragment](<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Firmware developer can easily port and enable a new board.<br><br><br> </span></p>)
@css[text-white fragment](<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Firmware code structure should be similar, no matter  the chipset / processor based architecture, i.e. embedded platform, a workstation or server </span></p>)
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Design open source EDK II  IA firmware<br><br>&nbsp;</span></p>)
@snapend

Note:

### Goals 
There is an existing myth that IA firmware is complex and hard to port or enable for a new platform. 
Goal is to provide some guidance on how to design open source EDK II  IA firmware solution

---?image=assets/images/slides/Slide5.JPG
@title[Four Focus Areas Section]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>Four Focus Areas</b>)</span></span></p>

@snap[north-east span-35 fragment]
<br>
<br>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Minimal /Full BIOS </span> </li>
  <li><span style="font-size:0.65em" >Feature ON/OFF </span> </li>
  <li><span style="font-size:0.65em" >Smbios/TPM/SecureBoot/ </span> </li>
  <li><span style="font-size:0.65em" >. . . </span> </li>
</ul>
@snapend

@snap[south-west span-30 fragment]
<br>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Setup Variable</span> </li>
  <li><span style="font-size:0.65em" >PCD </span> </li>
  <li><span style="font-size:0.65em" >Policy Hob/PPI/Protocol </span> </li>
</ul>
<br>
<br>
<br>
@snapend

@snap[south-east span-33 fragment]
<br>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >GPIO </span> </li>
  <li><span style="font-size:0.65em" >SIO </span> </li>
  <li><span style="font-size:0.65em" >ACPI </span> </li>
</ul>
<br>
<br>
<br>
<br>
@snapend



Note:
In order to provide suggestions on the problem statements earilier, we need to focus on the following four areas: 

- Feature. How does a BIOS provide the feature selection option to a developer? 
- Configuration. From which interface can a platform module get the configuration data? 
- Porting. Where are the modules to be ported for a new board? 
- Tree Structure. What does an EDKII platform package look like? 


---?image=assets/images/slides/Slide6.JPG
@title[Tree Structure Section]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>Tree Structure</b>)</span></span></p>


Note:
Tree Structure. What does an EDK II platform package look like? 


This is the directory structure of our EDK II platform in relationship to the whole and other areas, such as the boot flow, or kernel, or core.

---?image=assets/images/slides/Slide7.JPG
@title[Organization]
<p align="right"><span class="gold" >@size[1.1](<b>Organization</b>)</span></span></p>


@snap[north span-50 ]
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-30 ]
<br>
<br>
@box[bg-gold2 text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><b>Common</b><br><br>&nbsp;</span></p>)
@box[bg-gold2 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Platform</b><br><br>&nbsp;</span></p>)
@box[bg-gold2 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Board</b><br><br>&nbsp;</span></p>)
@box[bg-gold2 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Silicon</b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-67 ]
<br>
<br>
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; No direct HW requirements<br><br><br></span></p>)
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Enable a specific <br>&nbsp;&nbsp;&nbsp;platform's capabilities <br><br><br> </span></p>)
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Board specific code <br><br><br><br> </span></p>)
@css[text-white fragment](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" >&bull; Hardware specific code </span></p>)
@snapend


Note:
The architecture makes use of four primary classifications of code that are generally instantiated in different EDK II packages.
- Common (EDK II) is code that does not have any direct HW requirements other than the basics required to execute machine code on the processor (stack, memory, IA registers, etc).
   - Producer(s): TianoCore.org


- Platform defines the actions needed to enable a specific platform's capabilities. In this architecture, capabilities are divided into mandatory and advanced features. Mandatory features are enabled in stages prior to Stage VI. Advanced features are enabled in Stage VI and later.
  - Minimum Platform Producer(s): TianoCore.org
  - Advance Feature Producer(s): TianoCore.org, OEM, BIOS vendor
  - Board packages contains board specific code for one or more motherboards.
  - Producer(s): Device manufacturer, BIOS vendor, Board user

- Silicon, also often called hardware code, has some tie to a specific class of physical hardware. Sometimes governed by industry standards, sometimes proprietary. Silicon or hardware code is usually not intended to have multiple implementations for the same hardware.
  - Producer(s): Silicon vendor


---?image=assets/images/slides/Slide7.JPG
@title[Open Source EDK II Workspace]
<p align="right"><span class="gold" >@size[1.1](<b>Open Source EDK II Workspace</b>)</span></span></p>

@snap[north-west span-50 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north span-30 ]
<br>
<br>
@box[bg-gold2 text-white rounded my-box-pad2 fragment ](<p style="line-height:60% "><span style="font-size:0.9em;" ><b>Common</b><br><br>&nbsp;</span></p>)
@box[bg-gold2 text-white rounded my-box-pad2 fragment ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Platform</b><br><br>&nbsp;</span></p>)
@box[bg-gold2 text-white rounded my-box-pad2 fragment ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Board</b><br><br>&nbsp;</span></p>)
@box[bg-gold2 text-white rounded my-box-pad2 fragment ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>Silicon</b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-west span-60 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
&nbsp;MyWorkSpace/<br>&nbsp;&nbsp;
@color[yellow](edk2)/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  - "@color[#FFC000](<font face="Arial">edk2 Common</font>)"<br>&nbsp;&nbsp;
@color[yellow](edk2-platforms)/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Platform/ "@color[#FFC000](<font face="Arial">Platform</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       MinPlatformPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          BoardX/ "@color[#FFC000](<font face="Arial">Board</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/ "@color[#FFC000](<font face="Arial">Silicon</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       MinPlatformPkg/<br>&nbsp;&nbsp;
@color[yellow](edk2-non-osi)/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;
@color[yellow](FSP)/"@color[#FFC000](<font face="Arial">Silicon</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;
   . . ./<br>&nbsp;&nbsp;
</span></p>
@snapend


Note:
The build process creates
   this directory -> Build/
MyWorkSpace – directory from the "git" of repositories

Build –p .dsc from the BOARD Directory

The architecture is designed to support a maintainer ownership model. For example, board developers should not directly modify (fork) the platform, silicon, or common code. More details on conventional usage of the package classifications can be found in supplemental literature from UEFI Forum, TianoCore.org, and others.


---?image=assets/images/slides/Slide7.JPG
@title[Open Board Tree Structure]
<p align="right"><span class="gold" >@size[1.1](<b>Open Board Tree Structure</b>)</span></span></p>

@snap[north-west span-75 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend



@snap[north-west span-70 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
&nbsp;&nbsp;
@color[yellow](edk2-platforms)/  <a href="https://github.com/tianocore/edk2-platforms"> github.com/edk2-platforms</a><br>&nbsp;&nbsp;&nbsp;&nbsp;
  Platform/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       AdvancedFeaturePkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       KabylakeOpenBoardPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          KabylakeRvp3/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       MinPlatformPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       Vlv2TbltDevicePkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       KabylakeSiliconPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       &nbsp;. &nbsp;. &nbsp;./<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       Vlv2DeviceRefCodePkg/<br>&nbsp;&nbsp;
@color[yellow](edk2-non-osi)/<a href="https://github.com/tianocore/edk2-non-osi/tree/devel-MinPlatform">github.com/edk2-non-osi</a><br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;
@color[yellow](FSP)/<a href="https://github.com/IntelFsp/FSP">github.com/Intel/FSP</a><br>&nbsp;&nbsp;&nbsp;&nbsp;
   &nbsp;. &nbsp;. &nbsp;./<br>&nbsp;&nbsp;
</span></p>
@snapend


Note:
This is an example of the MinPlatform for the Intel Architecture (IA)
With Kabylake and  Vlv2TbltDevicePkg (Minnowboard MAX) as examples


Notice the 3 different repositories for the different sources align similarly to the COMMON, PLATFORM, BOARD & SILICON layout

Not shown is the edk2 repository since this should always be considered as common

---
@title[Directory Description]
<p align="right"><span class="gold" >@size[1.1](<b>Directory Description</b>)</span></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><b>@color[yellow](edk2-platform): </b>EDK II repo includes open source platform code </span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Platform folder : contains the platform specific modules by architecture</span> </li>
  <ul style="list-style-type:disc; line-height:0.7;">
    <li><span style="font-size:0.65em" >@color[cyan](MinPlatformPkg ): generic platform instance to control the boot flow.  </span> </li>
    <li><span style="font-size:0.65em" >@color[cyan](AdvancedFeaturePkg ): package to hold the advanced platform features </span> </li>
    <li><span style="font-size:0.65em" >@color[cyan](&lt;Generation&gt;OpenBoardPkg ): the silicon generation specific board package. All of the boards based upon this silicon generation can be located here </span> </li>
 </ul>
  <li><span style="font-size:0.65em" >Silicon folder : contains the silicon specific modules </span> </li>
  <ul style="list-style-type:disc; line-height:0.7;">
    <li><span style="font-size:0.65em" >@color[cyan](&lt;Generation&gt;SiliconPkg ): the silicon generation specific silicon package </span> </li>
  </ul>
</ul>

<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><b>@color[yellow](edk2-non-osi):</b> 
It is the EDK II repo to include any open platform modules which is in a binary format, such as FSP binary, or CPU microcode</span></p>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >@color[cyan](&lt;Generation&gt;SiliconBinPkg ):It is the silicon generation specific binary package. For example, CPU Microcode or the silicon binary FVs</span> </li>
</ul>


@snap[south span-95 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">&nbsp;Ideally, Only &lt;Generation&gt;OpenBoardPkg needs updating<br><br>&nbsp;</span></p>)
@snapend

Note:
- edk2-platform: EDK II repo to include any open source platform code, which has an  EDK II compatible license.
  - Platform folder: It contains the platform specific modules.
    - MinPlatformPkg: It is a generic platform instance to control the boot flow.
    - AdvancedFeaturePkg: It is a package to hold the advanced platform features. These features are not required for a basic OS boot, but they may be needed to provide a full feature platform firmware.
    - <Generation>OpenBoardPkg: It is the silicon generation specific board package. All of the boards based upon this silicon generation can be located here.
  - Silicon folder: It contains the silicon specific modules.
    - <Generation>SiliconPkg: It is the silicon generation specific silicon package.
- edk2-non-osi: It is the EDKII repo to include any open platform modules which is in a binary format, such as FSP binary, or CPU microcode.
  - <Generation>SiliconBinPkg: It is the silicon generation specific binary package. For example, CPU Microcode or the silicon binary FVs.

---
@title[FSP Directory Description]
<p align="right"><span class="gold" >@size[1.1](<b>FSP Directory Description</b>)</span></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><b>@color[yellow](FSP): </b>Intel FSP  repo includes FSP binary platform code </span></p>

<ul style="list-style-type:disc; line-height:0.8;">
  <li><span style="font-size:0.65em" >Platform folder Pkg : Each FSP project will be hosted in a separate directory</span> </li>
  <li><span style="font-size:0.65em" >ApolloLakeFspBinPkg Intel® Atom™ processor E3900 product family </span> </li>
  <li><span style="font-size:0.65em" >&nbsp;. &nbsp;. &nbsp;. </span> </li>
  <li><span style="font-size:0.65em" >CoffeeLakeFspBinPkg - 8th Generation Intel® Core™ processors and chipsets @size[.7em]( - formerly Coffee Lake and Whiskey Lake)<br> </span> </li>
  <li><span style="font-size:0.65em" >@color[cyan](KabylakeFspBinPkg ): 7th Generation Intel® Core™ processors and chipsets</span> </li>
  <ul style="list-style-type:disc; line-height:0.7;">
    <li><span style="font-size:0.65em" >Include </span> </li>
    <ul style="list-style-type:none; line-height:0.7;">
       <li><span style="font-size:0.65em" > - FSP UPD structure and related definitions used with EDK II build </span> </li>
	</ul>
    <li><span style="font-size:0.65em" >Doc - Integration Guide .PDF documentation </span> </li>
    <li><span style="font-size:0.65em" >@color[cyan](FSP.fd ) -Binary to be included with flash device image </span> </li>
    <li><span style="font-size:0.65em" >FSP.bsf - Configuration File with IDE configuration tool </span> </li>

  </ul>

</ul>


@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">FSP each project based on Intel Architecture <br><br>&nbsp;</span></p>)
@snapend

Note:

Intel® Firmware Support Package (Intel® FSP) includes: 
 A binary file 
 An integration guide 
 A rebasing tool 
 An IDE configuration tool / Boot Setting File (BSF) 


---
@title[Board Package Structure ]
<p align="right"><span class="gold" >@size[1.1](<b>Board Package Structure </b>)</span><span style="font-size:0.8em;" ><br>- `MinPlatformPkg`</span></p>

@snap[north-west span-45 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<p style="line-height:40% "><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
@color[cyan](MinPlatformPkg)  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &lt;BasicCommonFeature&gt;/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Include /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInit /<br>&nbsp;&nbsp;&nbsp;&nbsp;
</span></p>

<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Where: </span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >@color[yellow](&lt;BasicCommonFeature&gt; ): The basic features to support OS boot, such as ACPI, flash, and FspWrapper. It also includes the basic security features such as HSTI. </span> </li>
  <li><span style="font-size:0.65em" >@color[yellow](Include ): The include file as the package interface. All interfaces defined in MinPlatformPkg.dec are put to here.  </span> </li>
  <li><span style="font-size:0.65em" >@color[yellow](Library ): It only contains feature independent library, such as PeiLib. If a library is related to a feature, this library is put to <Feature>/Library folder, instead of root Library folder. </span> </li>
  <li><span style="font-size:0.65em" >@color[yellow](PlatformInit ): The common platform initialization module. There is PreMemPEI, PostMemPEI, DXE and SMM version. These modules control boot flow and provide some hook point to let board code do initialization. </span> </li>
</ul>
@snapend

@snap[north-east span-40 fragment]
<br>
<br>
<br>

@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:80%"><span style="font-size:0.8em">Basic Common Features<br>&nbsp;</span></p>)
@snapend

Note:

---
@title[Advanced Feature Package ]
<p align="right"><span class="gold" >@size[1.1](<b>Advanced Feature Package </b>)</span><span style="font-size:0.8em;" ><br></span></p>

@snap[north-west span-45 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<p style="line-height:40% "><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
@color[cyan](AdvancedFeaturePkg)  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &lt;AdvancedFeatureCommonFeature&gt;/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  Include /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Include /
</span></p>
<br>
<br>

<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Where: </span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >@color[yellow](&lt;AdvancedCommonFeature&gt; ): The advanced features, such as SMBIOS table, IPMI </span> </li>
  <li><span style="font-size:0.65em" >@color[yellow](Include ): The include file as the package interface.   </span> </li>
</ul>
@snapend



Note:


---
@title[Advanced Feature Package ]
<p align="right"><span class="gold" >@size[1.1](<b>Advanced Feature Package </b>)</span><span style="font-size:0.8em;" ><br></span></p>

@snap[north-west span-45 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<p style="line-height:40% "><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
@color[cyan](&lt;Generation&gt;OpenBoardPkg)  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &lt;BasicCommonBoardFeature&gt;/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Include /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  &lt;AdvancedCommonBoardFeature&gt; /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  @color[cyan](&lt;Board&gt;) /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    Include /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    &lt;BoardSpecificFeature&gt; /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    @color[cyan](OpenBoardPkg.dsc)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    @color[cyan](OpenBoardPkg.fdf)<br><br>
</span></p>

<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Where: </span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >@color[yellow](&lt;BasicCommonBoardFeature&gt; ) and @color[yellow](&lt;AdvancedCommonBoardFeature&gt; ): designate a board generation specific feature. They need to be updated when we enable a board generation. </span> </li>
  <li><span style="font-size:0.65em" >@color[yellow](&lt;Board&gt; ): contains all the board specific settings. If we need to port a new board in this generation, copy the &lt;Board&gt; folder and update the copy’s settings
  </span> </li>
</ul>
@snapend



Note:


---
@title[One Feature, one directory Guideline]
<p align="right"><span class="gold" >@size[1.1](<b>One Feature, one directory Guideline </b>)</span><span style="font-size:0.8em;" ><br></span></p>

@snap[north-west span-100 ]
<br>
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >Use a hierarchical layout , `KabylakeOpenBoardPkg` example</span></p>
@snapend

@snap[north-west span-45 ]
<br>
<br>
<br>
<br>
<p style="line-height:40% "><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
KabylakeOpenBoardPkg  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Acpi /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    BoardAcpiDxe /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  FspWapper /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PeiFspPolicyUpdateLib /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  @color[cyan](KabylakeRvp3) /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    BaseGpioExpanderLib / <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PeiI2cAccessLib  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Policy /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PolicyInitDxe /
</span></p>
@snapend


@snap[north-east span-55 ]
<br>
<br>
<br>
<br>
<p style="line-height:40% " align="left"><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
  @color[cyan](KabylakeRvp3) /<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;
    Include /<br>&nbsp;&nbsp;&nbsp;&nbsp;
    OpenBoardPkg.dsc  <br>&nbsp;&nbsp;&nbsp;&nbsp;
    OpenBoardPkg.fdf
</span></p>
@snapend


@snap[north-east span-55 fragment]
<br>
<br>
<br>
<br>
<p style="line-height:40% " align="left"><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  <br>&nbsp;&nbsp;&nbsp;&nbsp;
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @fa[long-arrow-alt-left fa-3x gp-bullet-yellow]
	<br>&nbsp;&nbsp;&nbsp;&nbsp;
   
</span></p>
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Only put the basic features into the root directory<br><br>&nbsp;</span></p>)
<br>
@snapend


Note:

Use a hierarchical layout - Specifically, only put the basic features into the root directory and put the advanced features into a "Features" directory. 

Slide shows the KabylakeOpenBoardPkg. 
The common board related ACPI is in Acpi directory. The common board related FSP policy update is in FspWrapper. The library folder includes the board specific GpioExpanderLib and I2cAccessLib. They might be used for other Kabylake generation board. 

The KabylakeRvp3 folder contains all RVP3 related settings, such as GPIO, High Definition Audio (HAD) verb Table, HsioPtss table, SPD table. This folder also has DSC and FDF file. We can build a KabylakeRvp3 binary inside of this folder 

---
@title[Compare to Minnowboard  MAX/Turbot]
<p align="right"><span class="gold" >@size[1.1](<b>Compare to Minnowboard  MAX/Turbot</b>)</span><span style="font-size:0.8em;" ><br></span></p>

@snap[north-west span-100 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend



@snap[north-west span-35 ]
<br>
<p style="line-height:40% "><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
@color[cyan](Vlv2TbltDevicePkg)  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   AcpiPlatform/<br>&nbsp;&nbsp;&nbsp;&nbsp;
   Application /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   BootScriptSaveDxe /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   FspAzaliaConfigData /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   FspSupport /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   FvbRuntimeDxe /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   FvInfoPei  /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   Include /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   IntelGopDepex /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   Library /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   Logo /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   Metronome /<br>&nbsp;&nbsp;&nbsp;&nbsp;
   MonoStatusCode /
</span></p>
@snapend

@snap[north span-35 ]
<br>
<p style="line-height:40% " align="left"><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
  Override /<br>&nbsp;&nbsp;
  PciPlatform /<br>&nbsp;&nbsp;
  PlatformCpuInfoDxe /<br>&nbsp;&nbsp;
  PlatformDxe /<br>&nbsp;&nbsp;
  PlatformGopPolicy /<br>&nbsp;&nbsp;
  PlatformInfoDxe /<br>&nbsp;&nbsp;
  PlatformInitPei /<br>&nbsp;&nbsp;
  PlatformPei /<br>&nbsp;&nbsp;
  PlatformSetupDxe /<br>&nbsp;&nbsp;
  PlatformSmm /<br>&nbsp;&nbsp;
  PpmPolicy /<br>&nbsp;&nbsp;
  SaveMemoryConfig /<br>&nbsp;&nbsp;
  SmBiosMiscDxe /<br>&nbsp;&nbsp;
</span></p>
@snapend


@snap[north-east span-35 ]
<br>
<p style="line-height:40% " align="left"><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
  SmmSwDispatch2OnSmm /<br>&nbsp;&nbsp;
  SwDispatchThunk /<br>&nbsp;&nbsp;
  SmramSaveInfoHandlerSmm /<br>&nbsp;&nbsp;
  Stitch /<br>&nbsp;&nbsp;
  UiApp /<br>&nbsp;&nbsp;
  VlvPlatformInitDxe /<br>&nbsp;&nbsp;
  Wpce791 /<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
  PlatformPkg.dec  <br>&nbsp;&nbsp;
  PlatformPkg.dsc  <br>&nbsp;&nbsp;
  PlatformPkg.fdf
</span></p>
@snapend


@snap[north-east span-25 fragment]
<br>
<p style="line-height:40% " align="left"><span style="font-size:0.5em; font-family:Consolas;" ><br>&nbsp;&nbsp;
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @fa[long-arrow-alt-left fa-3x gp-bullet-yellow]
  
</span></p>
@snapend

@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">This introduces issues when searching for a driver<br><br>&nbsp;</span></p>)
<br>
@snapend


Note:
This introduces issues when the developer wants to find a  particular driver. 


---?image=assets/images/slides/Slide17.JPG
@title[Focus - Features Section]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>Features</b>)</span></span></p>

@snap[north-east span-35 ]
<br>
<br>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Minimal /Full BIOS </span> </li>
  <li><span style="font-size:0.65em" >Feature ON/OFF </span> </li>
  <li><span style="font-size:0.65em" >Smbios/TPM/SecureBoot/ </span> </li>
  <li><span style="font-size:0.65em" >. . . </span> </li>
</ul>
@snapend





Note:
### Features

In order to provide suggestions on the problem statements above, we would like to focus on the following four areas: 
- Feature. How does a BIOS provide the feature selection option to a developer? 
- Configuration. From which interface can a platform module get the configuration data? 
- Porting. Where are the modules to be ported for a new board? 
- Tree Structure. What does an EDKII platform package look like? 


---?image=assets/images/slides/Slide18.JPG
@title[Feature –BIOS module selection]
<p align="right"><span class="gold" >@size[1.1](<b>Feature –BIOS module selection</b>)</span><span style="font-size:0.8em;" ><br></span></p>
<p style="line-height:40% " align="left"><span style="font-size:0.9em;" >Minimum set of features based on Categories </span></p>

@snap[north span-50 ]
<br>
<br>

<p style="line-height:20% " align="left"><span style="font-size:0.9em;" ><br></span></p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.8em;" ><b>&nbsp;</b><br>&nbsp;</span></p>)
<p style="line-height:20% " align="left"><span style="font-size:0.9em;" ><br><br></span></p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.8em;" ><b>&nbsp;</b><br>&nbsp;</span></p>)
<p style="line-height:20% " align="left"><span style="font-size:0.9em;" ><br><br></span></p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.8em;" ><b>&nbsp;</b><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-35 ]
<br>
<br>
<br>
@box[bg-lt-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:70% "><span style="font-size:0.8em;" ><b>Basic Boot Components &lpar;MIN&rpar;</b><br>&nbsp;</span></p>)
@box[bg-lt-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><b>Advance Boot components&lpar;Full&rpar; </b><br>&nbsp;</span></p>)
@box[bg-lt-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.8em;" ><b>Close Source</b><br><br>&nbsp;</span></p>)
@snapend



@snap[north-east span-62 fragment]
<br>
<br>

<p style="line-height:30% " align="left"><span style="font-size:0.9em;" ><br><br></span></p>
@css[text-white ](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" > UEFI, ACPI, PlatformInit<br><br><br><br></span></p>)
@css[text-white ](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" > SMBIOS, S3, OPAL <br> <br><br><br> </span></p>)
@css[text-white ](<p style="line-height:60%" align="left" ><span style="font-size:0.7em;" > TXT, AMT, CSM <br><br><br><br> </span></p>)

@snapend


@snap[south span-85 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Add / remove features using a build switch<br><br>&nbsp;</span></p>)
@snapend

Note:

- Minimal set (basic boot component) – this includes the minimal components needed to boot to the UEFI Shell or to a UEFI OS. The feature set is limited and may only include a basic ACPI table and some required platform initialization. 
- Full set (advanced boot component) – this entails all of the components needed to make a production BIOS. For example, it may support S3, SMBIOS table, OPAL. (Storage Work Group Storage Security Subsystem Class: Opal  - i.e. Tpm Opal)
- Most  advanced modules can be open source, too, but there might be a small portion of code that can not be open source, such as the binary elements used by TXT/AMT/CSM 


---?image=assets/images/slides/Slide20.JPG
@title[Basic Boot Components]
<p align="right"><span class="gold" >@size[1.1](<b>Basic Boot Components</b>)</span><span style="font-size:0.8em;" ><br></span></p>



Note:

Typically all the Intel Architecture platform firmware basic boot components are almost the same. In the slide, the GREEN part means the generic EDK II core modules. 
The YELLOW part means the silicon specific modules. And finally, the PURPLE part means the platform/board specific modules 


In the UEFI scope, we need the variable, timer, CPU, PCI, either SATA or USB as storage, Graphic or terminal as console output, and finally, USB/PS2 Keyboard or terminal as console input. The SMM portion is required for most X86 platforms in order to support UEFI Authenticated Variables [AUTH VARIABLE]. 
Most UEFI OSes also require ACPI, so ACPI tables and an SMM driver to enable/disable ACPI are needed. 
The platform may also need to initiliaze General Purpose Input/Ouput (GPIO) pins or a Super IO (SIO) to enable the basic boot functionality. 



---?image=assets/images/slides/Slide18.JPG
@title[Features Build Enabled]
<p align="right"><span class="gold" >@size[1.1](<b>Features Build Enabled</b>)</span><span style="font-size:0.8em;" ><br></span></p>

@snap[north-west span-85 ]
<br>
<br>
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">Platform-Board Build Scripts<br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-80]
<br>
<br>
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" >
Many Platforms have a bash or Python script  file to pre & post process the EDK II build process: 
<a href="https://github.com/tianocore/edk2-platforms/tree/master/Platform/Intel#build">Build Script</a></p>

<p style="line-height:60%" align="left" ><span style="font-size:0.75em;" >
Example: Invoked from the @size[.7em](`edk2-platforms/Platform/Intel`)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;
          @size[.7em](@color[#A8ff60](<b>`python build_bios.py –p <Board-name> `</b>))<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
               @size[.75em]( - uses config file @color[#A8ff60](`build.cfg`) from the @color[#A8ff60](`<Board-name>`) directory)<br>
			   <br>
</span></p>
@snapend

@snap[south-west span-100]
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" >
Configuration  Files:
</span></p>
<ul style="list-style-type:disc; line-height:0.6;">
  <li><span style="font-size:0.6em" > `edk2-platforms\Platform\Intel\build.cfg ` - contains the default settings </span> </li>
  <li><span style="font-size:0.6em" > Default settings are under the `DEFAULT_CONFIG` section</span> </li>
  <li><span style="font-size:0.6em" > Override the `edk2-platforms/Platform/Intel/. . ./build.cfg` settings from each board in board specific directory</span> </li>
</ul>
<br>
<br>
@snapend


Note:

### Building with the python script
- Open command window, go to the workspace directory, e.g. c:\Kabylake or ~/Kabylake in the case of a linux OS
- If using a linux OS
  - Type "cd edk2"
  - Type "source edksetup.sh"

- Type "cd ../" to go back to the workspace directory
- Type "cd edk2-platforms/Platform/Intel
- Type "python build_bios.py -p REPLACE_WITH_BOARD_NAME"



#### Configuration Files
The edk2-platforms\Platform\Intel\build.cfg file contains the default settings used by build_bios.py

The default settings are under the DEFAULT_CONFIG section

Each board can have a settings file that will override the edk2-platforms\Platform\Intel\build.cfg settings


An example of a board specific settings:
edk2-platforms\Platform\Intel\KabylakeOpenBoardPkg\KabylakeRvp3\build_config.cfg

---?image=assets/images/slides/Slide18.JPG
@title[Example Build config file]
<p align="right"><span class="gold" >@size[1.1](<b>Example Build config file</b>)</span><span style="font-size:0.8em;" ><br></span></p>

@snap[north-west span-80 ]
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-80 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
Kabylake example of Board specific settings:
</span></p>
<p style="line-height:50% " align="left"><span style="font-size:0.6em; font-family:Consolas;" >
&lt;workspace&gt;/edk2-platforms/\<br>&nbsp;
Platform/Intel/KabylakeOpenBoardPkg/\ <br>&nbsp;&nbsp;
KabylakeRvp3 /  @color[#A8ff60](build_config.cfg) <br></p>

<p style="line-height:40% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;&nbsp;
[CONFIG] <br>&nbsp;&nbsp;
WORKSPACE_PLATFORM_BIN = WORKSPACE_PLATFORM_BIN <br>&nbsp;&nbsp;
EDK_SETUP_OPTION = <br>&nbsp;&nbsp;
openssl_path = <br>&nbsp;&nbsp;
PLATFORM_BOARD_PACKAGE = KabylakeOpenBoardPkg <br>&nbsp;&nbsp;
PROJECT = KabylakeOpenBoardPkg/KabylakeRvp3 <br>&nbsp;&nbsp;
BOARD = KabylakeRvp3 <br>&nbsp;&nbsp;
FLASH_MAP_FDF = KabylakeOpenBoardPkg/Include/Fdf/FlashMapInclude.fdf <br>&nbsp;&nbsp;
PROJECT_DSC = KabylakeOpenBoardPkg/KabylakeRvp3/OpenBoardPkg.dsc <br>&nbsp;&nbsp;
BOARD_PKG_PCD_DSC = KabylakeOpenBoardPkg/KabylakeRvp3/OpenBoardPkgPcd.dsc <br>&nbsp;&nbsp;
ADDITIONAL_SCRIPTS = KabylakeOpenBoardPkg/KabylakeRvp3/build_board.py <br>&nbsp;&nbsp;
PrepRELEASE = DEBUG <br>&nbsp;&nbsp;
SILENT_MODE = FALSE <br>&nbsp;&nbsp;
&nbsp;.&nbsp;.&nbsp;.
</span></p>
@snapend


---?image=assets/images/slides/Slide18.JPG
@title[Platform Features Table d’hôte ]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Features Table d’hôte </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[south-west span-100 ]
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-80 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
Platform Firmware Boot Stage PCD in: <br><br><br>
@color[yellow](<b>`OpenBoardPkgConfig.dsc`</b>)
</span></p>

@snap[south-west span-100 ]
<p style="line-height:40% " align="left"></span><span style="font-size:0.45em; font-family:Consolas;" ><br>&nbsp;&nbsp;
[PcdsFixedAtBuild]<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Please select BootStage here.<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Stage 1 - enable debug (system deadloop after debug init)<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Stage 2 - mem init (system deadloop after mem init)<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Stage 3 - boot to UEFI shell only<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Stage 4 - boot to OS<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Stage 5 - boot to OS with security boot enabled<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &num; Stage 6 – Add Advanced features<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdBootStage)|4
</span></p>
<br>
@snapend


Note:

Features added via table d’hôte  by using a PCD. 
table d’hôte  Pronounced "Tab la dout"

Within the DSC and  FDF choose which modules to include based on PCD

Example
<pre>
DSC:
[PcdsFeatureFlag]
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterMemInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdUefiSecureBootEnable|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdTpm2Enable|FALSE

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 1
 gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|TRUE
!endif

Example FDF
!if gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly == FALSE
INF  MdeModulePkg/Universal/FaultTolerantWriteDxe/FaultTolerantWriteSmm.inf
INF  MdeModulePkg/Universal/Variable/RuntimeDxe/VariableSmmRuntimeDxe.inf
INF  MdeModulePkg/Universal/Variable/RuntimeDxe/VariableSmm.inf
!endif
</pre>


Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations


---?image=assets/images/slides/Slide18.JPG
@title[Platform Features à la cart with PCDs ]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Features à la cart with PCDs  </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[south-west span-100 ]
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-80 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
The Platform Config .dsc file controls if feature ON or OFF
<br><br>
Example:
<br>
@color[yellow](<b>`OpenBoardPkgConfig.dsc`</b> -  à la cart)
</span></p>

@snap[south-west span-100 ]
<p style="line-height:40% " align="left"></span><span style="font-size:0.45em; font-family:Consolas;" ><br>&nbsp;&nbsp;
[PcdsFeatureFlag]<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdStopAfterDebugInit)|FALSE <br>&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdStopAfterMemInit)|FALSE <br>&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdBootToShellOnly)|FALSE <br>&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdUefiSecureBootEnable)|FALSE <br>&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdTpm2Enable)|FALSE  <br>&nbsp;&nbsp;&nbsp;&nbsp;
!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 1 <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  gMinPlatformPkgTokenSpaceGuid.@color[yellow](PcdStopAfterDebugInit)|TRUE <br>&nbsp;&nbsp;&nbsp;&nbsp;
!endif <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 . &nbsp;&nbsp;.&nbsp;&nbsp; .

</span></p>
<br>
@snapend


Note:

At the same time, a platform firmware may provide an "à la cart" menu so that an advanced user can configure an individual item. For example, PcdUefiSecureBootEnable can be used to configure if a BIOS needs to support UEFI secure boot [AUTH VARIABLE]. PcdTpm2Enable can be used to configure if a BIOS needs to support the TPM2 [TPM2 EDKII]. 


---
@title[Where are the DSC & FDF files? ]
<p align="right"><span class="gold" >@size[1.1](<b>Where are the DSC & FDF files?</b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-45 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
Kabylake Open Board
</span></p>
<p style="line-height:40% " align="left"></span><span style="font-size:0.45em; font-family:Consolas;" ><br>&nbsp;&nbsp;
Platform/Intel /<br>&nbsp;&nbsp;&nbsp;
 KabyLakeOpenBoardPkg /<br>&nbsp;&nbsp;&nbsp;&nbsp;
 
  KabyLakeRvp3 /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkg@color[yellow](Config).dsc <br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

     OpenBoardPkgPcd.dsc  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkgBuildOption.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkg.dsc<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

     FlashMapInclude.fdf  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     OpenBoardPkg.fdf 

</span></p>

@snapend


@snap[north-east span-47 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
Minnowboard Turbot
</span></p>

<p style="line-height:40% " align="left"><span style="font-size:0.45em; font-family:Consolas;" ><br>&nbsp;&nbsp;
Platform/Intel /<br>&nbsp;&nbsp;&nbsp;&nbsp;

  Vlv2TbltDevicePkg /<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformPkg.dec<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

     PlatformPkg@color[yellow](Config).dsc<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

     PlatformPkgIa32.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformPkgX64.dsc<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformPkgGcc.dsc<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

     PlatformPkg.fdf <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     PlatformPkgGcc.fdf

</span></p>

@snapend

@snap[south span-95 fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:40%"><span style="font-size:0.8em">..Config.dsc File Controls if feature ON or OFF <br><br>&nbsp;</span></p>)
@snapend


Note:

---
@title[Example Kabylake Configuration .DSC file ]
<p align="right"><span class="gold" >@size[1.1](<b>Example Kabylake Configuration .DSC file</b>)</span><span style="font-size:0.8em;" ></span></p>

```
[PcdsFixedAtBuild]
  #
  # Please select BootStage here.
  # Stage 1 - enable debug (system deadloop after debug init)
  # Stage 2 - mem init (system deadloop after mem init)
  # Stage 3 - boot to shell only
  # Stage 4 - boot to OS
  # Stage 5 - boot to OS with security boot enabled
  #
  gMinPlatformPkgTokenSpaceGuid.PcdBootStage|4
  
[PcdsFeatureFlag]
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterMemInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdUefiSecureBootEnable|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdTpm2Enable|FALSE

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 1
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|TRUE
!endif

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 2
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterMemInit|TRUE
!endif
!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 3
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterMemInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly|TRUE
!endif

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 4
  gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly|FALSE
!endif

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 5
  gMinPlatformPkgTokenSpaceGuid.PcdUefiSecureBootEnable|TRUE
  gMinPlatformPkgTokenSpaceGuid.PcdTpm2Enable|TRUE
!endif
  
  gBoardModuleTokenSpaceGuid.PcdTbtEnable|FALSE
 
 
  gBoardModuleTokenSpaceGuid.PcdMultiBoardSupport|TRUE
 

```


@snap[south-east span-45 ]
<p style="line-height:40% " align="left"><span style="font-size:0.55em;">
Link to <a href="https://github.com/tianocore/edk2-platforms/blob/master/Platform/Intel/KabylakeOpenBoardPkg/KabylakeRvp3/OpenBoardPkgConfig.dsc">Confg .dsc </a>
file
</span></p>
@snapend

Note:

Click on link to view the whole .DSC file

---
@title[Example Kabylake Configuration .FDF file ]
<p align="right"><span class="gold" >@size[1.1](<b>Example Kabylake Configuration .FDF file</b>)</span><span style="font-size:0.8em;" ></span></p>

```
[FD.KabylakeRvp3]
 #
  . . .
[FV.FvPreMemory]
BlockSize          = $(FLASH_BLOCK_SIZE)
FvAlignment        = 16
  . . .
INF  UefiCpuPkg/SecCore/SecCore.inf
INF  MdeModulePkg/Core/Pei/PeiMain.inf
!include $(PLATFORM_PACKAGE)/Include/Fdf/CorePreMemoryInclude.fdf

INF $(PLATFORM_PACKAGE)/PlatformInit/ReportFv/ReportFvPei.inf
INF $(PLATFORM_PACKAGE)/PlatformInit/PlatformInitPei/PlatformInitPreMem.inf
INF IntelFsp2WrapperPkg/FspmWrapperPeim/FspmWrapperPeim.inf
INF $(PLATFORM_PACKAGE)/PlatformInit/SiliconPolicyPei/SiliconPolicyPeiPreMem.inf

. . .

[FV.FvPostMemoryUncompact]
BlockSize          = $(FLASH_BLOCK_SIZE)
FvAlignment        = 16
ERASE_POLARITY     = 1
 . . .

!include $(PLATFORM_PACKAGE)/Include/Fdf/CorePostMemoryInclude.fdf

# Init Board Config PCD
INF $(PLATFORM_PACKAGE)/PlatformInit/PlatformInitPei/PlatformInitPostMem.inf
INF IntelFsp2WrapperPkg/FspsWrapperPeim/FspsWrapperPeim.inf
INF $(PLATFORM_PACKAGE)/PlatformInit/SiliconPolicyPei/SiliconPolicyPeiPostMem.inf

  . . .

[FV.FvUefiBootUncompact]
BlockSize          = $(FLASH_BLOCK_SIZE)
FvAlignment        = 16
 . . .

!include $(PLATFORM_PACKAGE)/Include/Fdf/CoreUefiBootInclude.fdf

INF  UefiCpuPkg/CpuDxe/CpuDxe.inf
INF  MdeModulePkg/Bus/Pci/PciHostBridgeDxe/PciHostBridgeDxe.inf

INF  MdeModulePkg/Bus/Pci/SataControllerDxe/SataControllerDxe.inf
INF  MdeModulePkg/Bus/Ata/AtaBusDxe/AtaBusDxe.inf
INF  MdeModulePkg/Bus/Ata/AtaAtapiPassThru/AtaAtapiPassThru.inf
INF  MdeModulePkg/Universal/Console/GraphicsOutputDxe/GraphicsOutputDxe.inf

INF  ShellPkg/Application/Shell/Shell.inf

INF  $(PLATFORM_PACKAGE)/PlatformInit/PlatformInitDxe/PlatformInitDxe.inf
INF  IntelFsp2WrapperPkg/FspWrapperNotifyDxe/FspWrapperNotifyDxe.inf

INF  $(PLATFORM_PACKAGE)/Test/TestPointStubDxe/TestPointStubDxe.inf



```


@snap[south-east span-45 ]
<p style="line-height:40% " align="left"><span style="font-size:0.55em;">
Link to <a href="https://github.com/tianocore/edk2-platforms/blob/master/Platform/Intel/KabylakeOpenBoardPkg/KabylakeRvp3/OpenBoardPkg.fdf"> Kabylake .FDF </a>
file
</span></p>
@snapend

Note:

Click on the link to view the whole .FDF file


---?image=assets/images/slides/Slide28.JPG
@title[Focus - Configuration Section]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>Configuration </b>)</span></span></p>

@snap[south-west span-30 ]
<br>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Setup Variable</span> </li>
  <li><span style="font-size:0.65em" >PCD </span> </li>
  <li><span style="font-size:0.65em" >Policy Hob/PPI/Protocol </span> </li>
</ul>
<br>
<br>
<br>
@snapend


Note:
Configuration. From which interface can a platform module get the configuration data? 

there might be many sources of platform configuration data 

- Setup Variable
- PCD
- Policy Hob/PPI/Protocol

---
@title[Configuration Options ]
<p align="right"><span class="gold" >@size[1.1](<b>Configuration Options</b>)</span><span style="font-size:0.8em;" ></span></p>

<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >
There might be many sources of platform configuration data.  </span></p>

@snap[north-west span-30 ]
<br>
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >PI PCD <br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >UEFI Variable<br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >FSP UPD <br><br>&nbsp;</span></p>)
@snapend


@snap[north span-30 ]
<br>
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >Silicon Policy Hob/PPI/Protocol <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >Configuration Block <br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >Global NVS <br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-30 ]
<br>
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >Platform Signed Data Blob <br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >CMOS <br><br>&nbsp;</span></p>)
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" >MACRO <br><br>&nbsp;</span></p>)
@snapend



Note:
- PI PCD – The PI PCD could be static data fixed at build time or dynamic data updatable at runtime.
- UEFI Variable – The UEFI Variable can be non-volatile data or volatile data, and it is widely used by VFR.
- FSP UPD – FSP UPD can be static default configuration, or a dynamic updatable UPD.
- Silicon Policy Hob/PPI/Protocol – It is policy data constructed at runtime or it can be a hook for silicon code
- Configuration Block – It is a data structure to put all policy data in a block without any C-language data pointer in a policy data
- Global NVS – It is an ACPI region to pass the configuration from the C code to ASL code
- Platform signed data blob – It is read only signed data at build time.
- CMOS – It is simple non-volatile storage, but it is not secure
- MACRO – C-language MACRO. It is fixed at build time.


+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Configuration Options 02 ]
<p align="right"><span class="gold" >@size[1.1](<b>Configuration Options - details</b>)</span><span style="font-size:0.8em;" ></span></p>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >

@color[yellow](PI PCD) – The PI PCD could be static data fixed at build time or dynamic data updatable at runtime.<br><br>
@color[yellow](UEFI Variable) – The UEFI Variable can be non-volatile data or volatile data, and it is widely used by VFR.<br><br>
@color[yellow](FSP UPD) – FSP UPD can be static default configuration, or a dynamic updatable UPD.<br><br>
@color[yellow](Silicon Policy Hob/PPI/Protocol) – It is policy data constructed at runtime or it can be a hook for silicon code<br>
</span></p>

Note:

##### PI PCD – The PI PCD could be static data fixed at build time or dynamic data updatable at runtime. 
- PcdsFeatureFlag: This type PCD only supports 1/0. Caller uses FeaturePcdGet() to retrieve the value. This type of PCD is mapped to be a MACRO so that a compiler optimization can remove the code scoped by "if(FALSE)". It is not allowed to set as a PcdsFeatureFlag. 
- PcdsFixedAtBuild: This type of PCD can be mapped to a global variable if the caller uses PcdGet(), or a MACRO if the caller uses FixedPcdGet(). As such, this type of PCD can be used in a data structure definition. It is not allowed to be set as PcdsFixedAtBuild. 
- PcdsPatchableInModule: This type of PCD is mapped to a global variable. It is allowed for use by both PcdGet and PcdSet. If PcdSet is called, it only changes the module-level PCD value instead of a system-level PCD value. Only the current module sees the PCD change. Other modules still see the original value. 
- PcdsDynamicDefault: PcdsDynamicDefault is mapped to a PPI or protocol. It is allowed for both PcdGet and PcdSet. PcdSet changes the system-level PCD value immediately. This type of PCD value is volatile. The changed value will not be saved in the next boot. 
- PcdsDynamicHii: PcdsDynamicHii is mapped to a UEFI variable. It is non-volatile. As such, the changed value can be saved in the next boot. However, the tricky thing is that this PCD value depends on the UEFI variable services 

readiness. If PcdGet is called before UEFI variable services ready, the default PCD value will be returned instead of the updated PCD value. We suggest that the platform owner be very very careful of this trap. If DXE PcdGet is required before the UEFI variable services are ready, we suggest that the platform define PcdsDynamicDefault, and then use get variable data in the PEI phase to fill in this PCD value. 
- PcdsDynamicVpd: PcdsDynamicVpd is to map configuration data to a static flash region so that a tool can modify the PcdsDynamicVpd after the flash image is generated. This is used by a BIOS that needs to support binary configuration after build. Intel FSP is an example of using PcdsDynamicVpd. 
- PcdsDynamicEx: PcdsDynamicEx is to support external module for binary build. If an EFI module (DXE Driver or PEIM) is not built with the system firmware, the dynamic PCD must be declared as PcdsDynamicEx. If a platform wants to include this binary EFI module, the binary module INF must be included in DSC file. As such, the PCD database will include the external PCD declared in this binary module. 
- SkuIds: SkuIds is a special usage of PCD. The use case of Multi-SKU PCD is to build one UEFI firmware boots on multiple board with different configuration in each board. It can support multiple board configurations generated at build time and support runtime selection to make one configuration take effect finally. The good point is that it is very straightforward for each board, if board configuration can be determined. 
- DefaultStores: DefaultStores is a special usage of PCD (gEfiMdeModulePkgTokenSpaceGuid.PcdSetNvStoreDefaultId). The use case of DefaultStores is to create different default stores in different boot mode, such as standard boot, manufacturing boot mode, or safe boot mode. The configuration data is set to (gEfiMdeModulePkgTokenSpaceGuid.PcdNvStoreDefaultValueBuffer). All those default stores are configured at build time and selected at runtime according to the boot mode. The default store PCD can be consumed by the HiiDatabase to support BIOS setup "load default" operation. 


##### UEFI Variable – The UEFI Variable can be non-volatile data or volatile data, and it is widely used by VFR. 
- In most cases, a non-volatile variable is used to store the user updatable configuration in a setup page. One example is VT enable/disable. This is purely a platform choice. We suggest that the platform map variable configuration to PCD, and use a PcdSet callback to set the variable data. The benefit is that if a new platform just wants to use a static setting, it can remove the variable easily. 
- A non-volatile variable may also be used to store the system configuration generated at runtime, for example, memory configuration data. In order to maintain security, we suggest that platform to lock the configuration variable before exiting PM auth/EndOfDxe event, by using the EDKII_VARIABLE_LOCK protocol. 
- A volatile variable is generated at runtime. A platform setup driver may use this information to control a VFR page to suppress or gray out a menu, or to display the system information, like CPU/SA/PCH stepping and features. 

##### FSP UPD – FSP UPD can be static default configuration, or a dynamic updatable UPD. 
- FSP UPD is used to pass configuration from the FSP wrapper into a FSP binary. A platform needs to convert the policy configuration in PCD to a FSP UPD before calling a FSP API, like FspMemoryInit, FspSiliconInit. 
- PcdsDynamicVpd.Upd: For a FSP binary, we use DynamicVpd.Upd to mark the configuration that needs to be in the UPD region. (Please be aware that UPD is not a standard PCD concept, it is an FSP extension) 

##### Silicon Policy Hob/PPI/Protocol – It is policy data constructed at runtime or it can be a hook for silicon code. 
- Policy data: Silicon Policy Hob/PPI/Protocol are useful in order to let one silicon code module support multiple boards. It is the interface between silicon code and platform code. A platform needs to convert policy configuration in PCD into a Silicon Policy PPI/Protocol. 
- Silicon Hook: Sometimes, we observe that Silicon Policy PPI or Protocol provides a silicon hook for platform. This hook may perform some additional action based on a platform setting, or retrieve some system information. In most cases, we suggest to separate the hook function from policy data. 

+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Configuration Options 03 ]
<p align="right"><span class="gold" >@size[1.1](<b>Configuration Options - details Cont.</b>)</span><span style="font-size:0.8em;" ></span></p>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >
@color[yellow](Configuration Block) – It is a data structure to put all policy data in a block without any C-language data pointer in a policy data <br><br>
@color[yellow](Global NVS) – It is an ACPI region to pass the configuration from the C code to ASL code <br><br>
@color[yellow](Platform signed data blob) – It is read only signed data at build time.<br><br>
@color[yellow](CMOS) – It is simple non-volatile storage, but it is not secure <br><br>
@color[yellow](MACRO) – C-language MACRO. It is fixed at build time<br>
</span></p>

Note:

##### Configuration Block – It is a data structure to put all policy data in a block without any C-language data pointer in a policy data. 
- The Configuration Block is a new idea to resolve data pointer issues objserved in earlier HOB usage. Previously, a silicon code module would define a root policy data object with some data pointers to sub-regions. For example, a PCH policy data may include a pointer to USB policy data, a pointer to SATA policy data, and a pointer to PCIExpress policy data. This HOB policy data pointer needs to be relocated after memory initialization, such as the Memory Reference Code (MRC), is done, because the PEI core needs to move data from temporary memory or Cache-As-RAM (CAR) to DRAM. If the platform code forgets to move the policy data and fix the pointer, the following code might retrieve the wrong policy data pointer. With the configuration block, the silicon and platform needn’t worry about the invalid policy data pointer issue because the data pointer is eliminated. The PCH policy data block may include a USB policy data block, a SATA policy data and a PCIExpress policy data. Configuration Blocks can be mapped and used by either Hob/PPI/Protocol or PCD. 
##### Global NVS – It is an ACPI region to pass the configuration from the C code to ASL code. 
- Global NVS can be used for turning some feature on/off. An example includes returning different _STA values. 0x0 means the device does not exist. 0xF means the device exists. 

It can be used as the policy data, for example CriticalTemperature value. A platform C code module may convert the configuration from PCD to Global NVS. 
- Since the name has "global", we observe that may platform put all different features into one big data structure. It is discouraged. We recommend each separate feature can have its own NVS data structure. It is easy for feature on/off control. 

##### Platform signed data blob – It is read only signed data at build time. 

This signed data blob provides the configuration on a platform. An OEM may update the configuration for different boards. We suggest the platform map the signed data blob to PCDs so that a platform consumer can just use PcdGet to get the configuration without knowing the data source. The benefit is that all the platform code can be consistent, irrespective of whether the configuration data is from a signed data blob, a BIOS boot block static region, or a UEFI variable. 
##### CMOS – It is simple non-volatile storage, but it is not secure. 
- The most useful usage of CMOS is to use CMOS-CLEAR to determine if an end user wants to use the default variable configuration. This is a consistent user experience from old legacy BIOS. The new platform can use a special function key or a special GPIO as indicator of this logic. 
- The benefit of CMOS is that the CMOS can be accessed at early SEC phase without rich API requirements. Beyond that usage, though, we do not suggest a platform use CMOS to store configuration data. 
##### MACRO – C-language MACRO. It is fixed at build time. 
- A MACRO can be used as static data configuration. It is useful if the MACRO is only used in one module and does not require user configuration. However, if the MACRO is used across many modules or is configurable, like PCIE_BASE, we suggest using PCD. 
- A MACRO used in #IFDEF can be used to enable/disable features. If the consumer is in C code, it can be replaced by FeaturePcd. It will become if(0) or if(1) finally. The benefit of using PCD is that all the code in both path can be built. 


---
@title[Use PCD instead of UEFI Variable  ]
<p align="right"><span class="gold" >@size[1.1](<b>Use PCD instead of UEFI Variable </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-45 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
@color[cyan](UEFI Variable)
</span></p>

<p style="line-height:40% " align="left"></span><span style="font-size:0.45em; font-family:Consolas;" ><br>&nbsp;&nbsp;
 //<br>&nbsp;&nbsp;
 // Get config from setup variable<br>&nbsp;&nbsp;
 //<br>&nbsp;&nbsp;
 VarDataSize = sizeof (SETUP_DATA);<br>&nbsp;&nbsp;
 Status = GetVariable (<br>&nbsp;&nbsp;&nbsp;&nbsp;
	L"Setup",<br>&nbsp;&nbsp;&nbsp;&nbsp;
	&amp;gSetupVariableGuid,<br>&nbsp;&nbsp;&nbsp;&nbsp;
	NULL,<br>&nbsp;&nbsp;&nbsp;&nbsp;
	&amp;VarDataSize,<br>&nbsp;&nbsp;&nbsp;&nbsp;
	&amp;mSystemConfiguration<br>&nbsp;&nbsp;
 );<br>&nbsp;&nbsp;
</span></p> 
@snapend


@snap[north-east span-47 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br>
@color[cyan](PCD)
</span></p>

<p style="line-height:40% " align="left"></span><span style="font-size:0.45em; font-family:Consolas;" ><br>&nbsp;&nbsp;
 //<br>&nbsp;&nbsp;
 // Get setup configuration from PCD<br>&nbsp;&nbsp;
 //<br>&nbsp;&nbsp;
 CopyMem (<br>&nbsp;&nbsp;&nbsp;&nbsp;
	&amp;mSystemConfiguration,<br>&nbsp;&nbsp;&nbsp;&nbsp;
	PcdGetPtr (PcdSetupConfiguration),<br>&nbsp;&nbsp;&nbsp;&nbsp;
	sizeof(mSystemConfiguration)<br>&nbsp;&nbsp;&nbsp;&nbsp;
 );
</span></p> 
@snapend


Note:

IF UEFI Variable is used, people then have to remember clearly on which configuration is stored in which direct location. Also if a platform decides to change the configuration source from one place (UEFI variable) to another (static region in boot block), all impacted platform modules are required to change. This is non-ideal for source code maintenance and development. 

BKM is using PCDs only in platform code, no matter where a platform chooses to store configuration data based upon the production requirement, 


Then the code is consistent and easy to maintain, especially if the next generation platform decides to change the location. 

---?image=/assets/images/slides/Slide33.JPG
@title[PCD Syntax review]
<p align="right"><span class="gold" ><b>PCD Syntax Review</b></span></p>
@snap[north-east span-90 fragment]
<br>
<br>
<p align="left" style="line-height:80%"><span style="font-size:0.9em; ">PCD defined in the DEC file from any package</span></p>
@box[bg-black text-white my-box-pad2  ](<p style="line-height:40%" align="left"><span style="font-size:0.450em; font-family:Consolas; " >&nbsp;&nbsp;[Guids.common]<br>&nbsp;&nbsp;@color[red](PcdTokenSpaceGuidName)={ 0xXXXXXXXX, 0xXXXX, 0xXXXX, { 0xXX, . . .}}<br>&nbsp;&nbsp;. . .<br>&nbsp;&nbsp;[Pcds...]<br>&nbsp;&nbsp;PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaxSize]]|Token<br>&nbsp;&nbsp;</span></p>)
<br>
@snapend

@snap[north-east span-90 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p align="left" style="line-height:80%"><span style="font-size:0.9em; ">PCD usage listed in INF file for module</span></p>
@box[bg-black text-white my-box-pad2  ](<p style="line-height:40%" align="left"><span style="font-size:0.450em; font-family:Consolas; " >&nbsp;&nbsp;[...Pcds...]<br>&nbsp;&nbsp;PcdTokenSpaceGuidName.@color[red](PcdTokenName)|[Value]<br>&nbsp;&nbsp;</span></p>)
<br>
@snapend


@snap[north-east span-90 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p align="left" style="line-height:80%"><span style="font-size:0.9em; ">Value of PCD set in @color[yellow](<b>`OpenBoardPkg. . .dsc`</b>)</span></p>
@box[bg-black text-white my-box-pad2  ](<p style="line-height:40%" align="left"><span style="font-size:0.450em; font-family:Consolas; " >&nbsp;&nbsp;[Pcds...]<br>&nbsp;&nbsp;PcdTokenSpaceGuidName.@color[red](PcdTokenName)|@color[cyan](Value)[|DatumType[|MaximumDatumSize]]</span><br>&nbsp;&nbsp;</p>)
<br>
@snapend



Note:

BKM is to set the desired value in the Platform Specific .DSC file


- PCD defined in the DEC file from any package
- [Guids.common]
   - PcdTokenSpaceGuidName={ 0x914AEBE7, 0x4635, 0x459b, { 0xAA, . . .}}

- [Pcds...]
  - PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaxSize]]|Token
  - PCD usage listed in INF file for module
- […Pcd…] 
  - PcdTokenSpaceGuidName.PcdTokenName|[Value]
  - Value of PCD set in NewPlatform.dsc
- [Pcds...]
  - PcdTokenSpaceGuidName.PcdTokenName|Value[|DatumType[|MaximumDatumSize]]
- Example used in new OpenBoardPkg.dsc
- [PcdsFixedAtBuild.IA32]
  -  gEfiIchTokenSpaceGuid.PcdIchAcpiIoPortBaseAddress|0x400
  -  gNewProjectTokenSpaceGuid.PcdFlashAreaBaseAddress|0xFFF00000
  - gNewProjectTokenSpaceGuid.PcdFlashAreaSize|0x100000


 
---?image=/assets/images/slides/Slide34.JPG
@title[How to Map PCD ]
<p align="right"><span class="gold" >@size[1.1](<b>How to Map PCD to Configuration Data</b>)</span><span style="font-size:0.8em;" ></span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >
Using "@color[yellow](Callback)" mechanism to convert PCD to Configuration data
</span></p>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" >
No examples currently available
</span></p>



Note:

A PCD driver can provide a callback function on PcdSet(). 
A platform may introduce a "ConfigConvert" module (GREEN box). The logic runs early and calls PcdSet() to convert other storage data (variable, signed data blob, policy hob) to the PCD database. 

Then the rest of PlatformInit code (YELLOW box) can just call PcdGet() to get the policy data. 

If the Platform driver wants to update a PCD value by calling PcdSet() later, the "ConfigConvert" can register a PCD callback function to redirect setting to other source (for example, variable). 

The Key Point is that the purpose of the configuration conversion is that any other platform driver should use PcdGet() to retrieve policy data, and PcdSet() to update policy data. 

KabylakeOpenBoardPkg does not use a UEFI variable to save the configuration data, but this might be used for other real platforms. 


---
@title["C" Data Structure as PCDs ]
<p align="right"><span class="gold" >@size[1.1](<b>"C" Data Structure as PCDs</b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-100 ]
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-100 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" ><br>
Example: `AdvancedFeaturePkg.dec`  for SMBIOS type 0 data structure
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" >&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation| \<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        {0x0}|@color[yellow](SMBIOS_TABLE_TYPE0)|0x80010000 {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    &lt;HeaderFiles&gt;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       IndustryStandard/@color[yellow](SmBios.h)<br>&nbsp;&nbsp;&nbsp;&nbsp;
    &lt;Packages&gt;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       MdePkg/MdePkg.dec<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       AdvancedFeaturePkg/AdvancedFeaturePkg.dec<br>&nbsp;&nbsp;
}<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.Vendor|0x1<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.BiosVersion|0x2<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.BiosSegment|0xF000<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.BiosReleaseDate|0x3<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.BiosSize|0xFF<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.BiosCharacteristics.\<br>&nbsp;&nbsp;&nbsp;&nbsp;
     PciIsSupported|1<br>&nbsp;&nbsp;
gAdvancedFeaturePkgTokenSpaceGuid.PcdSmbiosType0BiosInformation.BiosCharacteristics.\<br>&nbsp;&nbsp;&nbsp;&nbsp;
     PlugAndPlayIsSupported|1
</span></p>




Note:

In the latest EDKII, the developer can associate a PCD to a C data structure and assign the value to each sub-field directly. 

MinPlatform AdvancedFeaturePkg  .DEC file defines a set of PCD for SMBIOS table data structure. Each field has its own default value. 

By using the structure PCD, a platform may define a global configuration PCD and assign the policy data in DSC file directly. 

From SmBios.h 
<pre>
typedef struct {
  SMBIOS_STRUCTURE          Hdr;
  SMBIOS_TABLE_STRING       Vendor;
  SMBIOS_TABLE_STRING       BiosVersion;
  UINT16                    BiosSegment;
  SMBIOS_TABLE_STRING       BiosReleaseDate;
  UINT8                     BiosSize;
  MISC_BIOS_CHARACTERISTICS BiosCharacteristics;
  UINT8                     BIOSCharacteristicsExtensionBytes[2];
  UINT8                     SystemBiosMajorRelease;
  UINT8                     SystemBiosMinorRelease;
  UINT8                     EmbeddedControllerFirmwareMajorRelease;
  UINT8                     EmbeddedControllerFirmwareMinorRelease;
  //
  // Add for smbios 3.1.0
  //
  EXTENDED_BIOS_ROM_SIZE    ExtendedBiosSize;
} SMBIOS_TABLE_TYPE0;

</pre>

---
@title[Example of DSC xRef DEC & .h  files  ]
<p align="right"><span class="gold" >@size[1.1](<b>Example of DSC xRef DEC & .h  files </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-47 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](Purly Pkg  DEC File)<br>
@size[.8em](&num;&num; `gEfiSetupVariableGuid`)
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" >&nbsp;&nbsp;
 OemSkuTokenSpaceGuid.PcdSetupData|{0x0}|\<br>&nbsp;&nbsp;
 @color[yellow](SYSTEM_CONFIGURATION)|0x000F0001 &lbrace; <br>&nbsp;&nbsp;
    &lt;HeaderFiles&gt; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      Guid/@color[yellow](SetupVariable.h)  <br>&nbsp;&nbsp;&nbsp;&nbsp;
    &lt;Packages&gt;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      MdePkg/MdePkg.dec<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PurleyRcPkg/RcPkg.dec<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PurleySktPkg/SocketPkg.dec<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      LewisburgPkg/PchRcPkg.dec<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      PurleyOpenBoardPkg/PlatPkg.dec<br>&nbsp;&nbsp;
  &rbrace;<br><br>
<font face="Arial">@size[1.5em](@color[cyan](&nbsp;&nbsp;"C" SetupVariable.h File  )) </font>
<br>
&nbsp;&nbsp;.&nbsp; . &nbsp;.<br>&nbsp;&nbsp;&nbsp;&nbsp;
   UINT8    FanPwmOffset; <br>&nbsp;&nbsp;&nbsp;&nbsp;
   UINT8    WakeOnLanSupport;<br>&nbsp;&nbsp;&nbsp;&nbsp;
   UINT8    Use1GPageTable;<br>&nbsp;&nbsp;&nbsp;&nbsp;
   UINT8    CloudProfile;<br>&nbsp;&nbsp;
} @color[yellow](SYSTEM_CONFIGURATION);
</span></p> 
@snapend


@snap[north-east span-47 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](StructureConfig.DSC File)
</span></p>
<br>
<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;&nbsp;
gOemSkuTokenSpaceGuid.PcdSetupData.\<br>&nbsp;&nbsp;
@color[#ff0000](CloudProfile)|0x0 <br>
<br>&nbsp;&nbsp;
gOemSkuTokenSpaceGuid.PcdSetupData.\<br>&nbsp;&nbsp;
@color[#ff0000](Use1GPageTable)|0x1<br>
<br>&nbsp;&nbsp;
gOemSkuTokenSpaceGuid.PcdSetupData.\<br>&nbsp;&nbsp;
@color[#ff0000](FanPwmOffset)|0x0 <br>
<br>&nbsp;&nbsp;
gOemSkuTokenSpaceGuid.PcdSetupData.\<br>&nbsp;&nbsp;
@color[#ff0000](WakeOnLanSupport)|0x0
<br>&nbsp;&nbsp;
. &nbsp;. &nbsp;.

</span></p> 
@snapend


Note:

---
@title[Configuration Multi-SKU PCD – Board ID  ]
<p align="right"><span class="gold" >@size[1.1](<b>Configuration Multi-SKU PCD – Board ID </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-49 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-48 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](DSC File – SKU Set at BUILD time)
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;&nbsp;
 .&nbsp;.&nbsp;.<br>&nbsp;&nbsp;
SKUID_IDENTIFIER = ?<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[SkuIds]<br>&nbsp;&nbsp;
0|DEFAULT<br>&nbsp;&nbsp;
4|BoardX<br>&nbsp;&nbsp;
0x42|BoardY<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[PcdsDynamicDefault.common.@color[yellow](BoardX)]<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioPin|0x8<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioInitValue|\<br>&nbsp;&nbsp;&nbsp;&nbsp;
        &lbrace;0x00, 0x04, 0x02, 0x04, ...&rbrace;<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[PcdsDynamicDefault.common.@color[yellow](BoardY)]<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioPin|0x4<br>&nbsp;&nbsp;
gBoardModuleTokenSpaceGuid.PcdGpioInitValue|\<br>&nbsp;&nbsp;&nbsp;&nbsp;
        &lbrace;0x00, 0x02, 0x01, 0x02, ...&rbrace;<br>&nbsp;&nbsp;
</span></p> 
@snapend


@snap[north-east span-47 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](SKU PCD Set Dynamically)
</span></p>
<br>
<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" >
&nbsp;&nbsp;
BoardXBoardDetect( VOID)<br>&nbsp;&nbsp;
&lbrace;<br>&nbsp;&nbsp;
. . .<br>&nbsp;&nbsp;&nbsp;&nbsp;
  if (@color[yellow](LibPcdGetSku) () != 0) &lbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    return EFI_SUCCESS;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &rbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;
  if (IsBoardX ()) &lbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     @color[yellow](LibPcdSetSku) (BoardIdIsBoardX);<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ASSERT (LibPcdGetSku() == <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
              BoardIdIsBoardX);<br>&nbsp;&nbsp;&nbsp;&nbsp;
  &rbrace;<br>&nbsp;&nbsp;&nbsp;&nbsp;
  return EFI_SUCCESS;<br>&nbsp;&nbsp;
&rbrace;<br>&nbsp;&nbsp;
</span></p> 
@snapend


Note:
SkuIds is a special usage of PCD. It can support multiple configurations generated at build time, and it supports runtime selection to make one configuration take effect finally. 

Multi-sku PCD concept is defined by PI specification Volume 3, Chapter 8 PCD, EFI_PCD_PROTOCOL.SetSku (). 

The SKU PCD is actually a dynamic PCD. During boot, the board detection takes the responsibility to set the SKU. Once the SKU PCD is set, the configuration associated with this SKU takes effect immediately 

---
@title[Default Stores PCD – for Configuration   ]
<p align="right"><span class="gold" >@size[1.1](<b>Default Stores PCD – for Configuration  </b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-100 ]
<br>
<br>
<br>
<br>

@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend



@snap[north-west span-100 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>
@color[cyan](DSC File – )
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;&nbsp;
 .&nbsp;.&nbsp;.<br>&nbsp;&nbsp;
VPD_TOOL_GUID  = 8C3D856A-9 . . .<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[DefaultStores]<br>&nbsp;&nbsp;
0|STANDARD<br>&nbsp;&nbsp;
1|MANUFACTURING<br>&nbsp;&nbsp;
2|SAFE<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
<br>&nbsp;&nbsp;
[PcdsDynamicExVpd.common.@color[yellow](DEFAULT)]<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gEfiMdeModulePkgTokenSpaceGuid.PcdNvStoreDefaultValueBuffer|*<br>&nbsp;&nbsp;
[PcdsDynamicEx.common.DEFAULT.@color[yellow](STANDARD)]<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gOemSkuTokenSpaceGuid.PcdSetupData.CloudProfile|0x0<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gOemSkuTokenSpaceGuid.PcdSetupData.Use1GPageTable|0x1<br>&nbsp;&nbsp;
[PcdsDynamicEx.common.DEFAULT.@color[yellow](MANUFACTURING)]<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gOemSkuTokenSpaceGuid.PcdSetupData.CloudProfile|0x1<br>&nbsp;&nbsp;&nbsp;&nbsp;
  gOemSkuTokenSpaceGuid.PcdSetupData.Use1GPageTable|0x0<br>&nbsp;&nbsp;

</span></p> 
@snapend


@snap[north-east span-45 fragment ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br><br>
&nbsp;
</span></p>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Special PCD to support the default stores concept in UEFI specification</span> </li>
  <li><span style="font-size:0.65em" >Can be Dynamically set</span> </li>
</ul>
@snapend


Note:
DefaultStores PCD is a special PCD to support the default stores concept in UEFI specification, Chapter 32 Human Interface Infrastructure. Per UEFI specification, there are 3 standard default stores: Standard Default, Manufacturing Default, and Safe Default 

VPD_TOOL_GUID = 8C3D856A-9BE6-468E-850A-24F7A8D38E08 

#### fdf file 
<pre>
[FD.Platform] 
... 
0x00C50000|0x00030000 
gEfiMdeModulePkgTokenSpaceGuid.PcdVpdBaseAddress 
FILE = $(OUTPUT_DIRECTORY)/$(TARGET)_$(TOOL_CHAIN_TAG)/FV/8C3D856A-9BE6-468E-850A-24F7A8D38E08.bin 
</pre>

Dynampic set in BoardInitPreMem function
PcdSet16S (PcdSetNvStoreDefaultId 
 When its value is set in PEI, it will trig the default setting to be applied as the default EFI variable.

---
@title[Silicon Policy data flow guidelines]
<p align="right"><span class="gold" >@size[1.1](<b>Silicon Policy data flow guidelines</b>)</span></span></p>

@snap[north-east span-60 ]
<br>
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:70%" align="left"><span style="font-size:0.7em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
<p style="line-height:70%" align="left"><br><br>&nbsp; </p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:70%" align="left"><span style="font-size:0.7em;" ><b>&nbsp;</b><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-45 ]
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.9em;" ><b>&nbsp;Silicon Module Provides<br>&nbsp; Default Silicon Policy Data</b><br>&nbsp;</span></p>)
<p style="line-height:70%" align="left"><br>&nbsp; </p>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%"><span style="font-size:0.9em;" ><b>&nbsp;Board Module Updates <br>&nbsp;the Silicon Policy Data </b><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-50 ]
<br>
<br>
<br>
<p style="line-height:70%" align="left"><span style="font-size:0.7em;" ><b>`Typedef` data structure</b><br><br>&nbsp;</span></p>
<p style="line-height:70%" align="left"><br><br><br>&nbsp; </p>
<p style="line-height:70%" align="left"><span style="font-size:0.7em;" ><b>PCD database, Setup Variable, Binary Blob, etc.</b><br><br>&nbsp;</span></p>
@snapend


Note:

Silicon policy data update is one of the most important tasks as part of bringing up a board. In order to make the board enablement more efficient, we have the below guidelines: 


## Silicon Module Provides Default Silicon Policy Data 

A silicon policy data object is created per Silicon module. The data structure should only contain the data. Functions should not be used in silicon policy data. 
When a silicon module installs this policy data, it should consider the most common usage as the default policy data. 



## Board Module Updates the Silicon Policy Data 

A board module may get default silicon policy data structures and update them. 

A board module may refer to another source to get the board specific policy data, including but not limited to: 
- PCD database 
- Setup Variable 
- Binary Blob 
- Built-in C structure. 

---?image=assets/images/slides/Slide40.JPG
@title[Example: FSP policy in MinPlatformPkg]
<p align="right"><span class="gold" >@size[1.1](<b>Example: FSP policy in MinPlatformPkg</b>)</span></span></p>


Note:
Take FSP policy in MinPlatformPkg is an example. 

Therein we defined FspPolicyInitLib (FspPolicyInitLib.h) and FspPolicyUpdateLib (FspPolicyUpdateLib.h). 

When the FSP wrapper wants to call MemoryInitAPI, it calls UpdateFspmUpdData() (PeiFspWrapperPlatformLib.c) to get the UPD configuration. 

Then FspmPolicyInit() and FspmPolicyUpdate() are invoked. 

The KabylakeSiliconPkg provides the former (PeiFspPolicyInitLib.c), and KabylakeOpenBoardPkg provides the latter (PeiFspPolicyUpdateLib.c).


---
@title[Update Silicon Policy example ]
<p align="right"><span class="gold" >@size[1.1](<b>Update Silicon Policy example</b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[north-west span-49 ]
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-49 ]
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-100 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" ><br><br>
KabylakeOpenBoardPkg/FspWrapper/Library/PeiSiliconPolicyUpdateLibFsp
</span></p>
@snapend


@snap[north-west span-47 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>&nbsp;
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;&nbsp;
EFI_STATUS<br>&nbsp;&nbsp;
EFIAPI <br>&nbsp;&nbsp;
PeiFspSaPolicyUpdatePreMem ( <br>&nbsp;&nbsp;
IN OUT FSPM_UPD &ast;FspmUpd <br>&nbsp;&nbsp;
) <br>&nbsp;&nbsp;
&lbrace; <br>&nbsp;&nbsp;
VOID &ast;Buffer; <br>&nbsp;&nbsp;
// @color[#A8ff60](<font face="Arial">Override MemorySpdPtr</font>)<br>&nbsp;&nbsp;
CopyMem((VOID &ast;)(UINTN)\  <br>&nbsp;&nbsp;&nbsp;&nbsp;
 FspmUpd-&gt;FspmConfig.MemorySpdPtr00,\ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 (VOID *)(UINTN)PcdGet32(PcdMrcSpdData),\ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 @color[yellow](PcdGet16) (PcdMrcSpdDataSize)); <br>&nbsp;&nbsp;
CopyMem((VOID &ast;)(UINTN)\ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 FspmUpd-&gt;FspmConfig.MemorySpdPtr10,\ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 (VOID &ast;)(UINTN)PcdGet32 (PcdMrcSpdData),\ <br>&nbsp;&nbsp;&nbsp;&nbsp;
 @color[yellow](PcdGet16) (PcdMrcSpdDataSize)); <br>&nbsp;&nbsp;
</span></p> 
@snapend


@snap[north-east span-47 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" ><br><br>&nbsp;
</span></p>

<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" >
<br>
<br>&nbsp;&nbsp;
@color[#A8ff60](. . .) <br>&nbsp;&nbsp;
// @color[#A8ff60](<font face="Arial">Updating Dq Pins Interleaved,Rcomp</font>) <br>&nbsp;&nbsp;
// @color[#A8ff60](<font face="Arial">Resistor &amp; Rcomp Target Settings </font>)<br>&nbsp;&nbsp;
  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  Buffer = (VOID &ast;) (UINTN) @color[yellow](PcdGet32) \      <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          (PcdMrcRcompTarget);  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  if (Buffer) &lbrace; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    CopyMem ((VOID &ast;)\ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      FspmUpd-&gt;FspmConfig.RcompTarget, \ <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      Buffer, 10);  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  &rbrace;  <br>&nbsp;&nbsp;&nbsp;&nbsp;
  return EFI_SUCCESS;  <br>&nbsp;&nbsp;
&rbrace;  
</span></p> 
@snapend


@snap[south-east span-35 ]
<p style="line-height:35% " align="left"></span><span style="font-size:0.4em;" >
Link to file: <a href="https://github.com/tianocore/edk2-platforms/blob/master/Platform/Intel/KabylakeOpenBoardPkg/FspWrapper/Library/PeiSiliconPolicyUpdateLibFsp/PeiSaPolicyUpdatePreMem.c">
PeiSaPolicyUpdatePrMem.c</a>
</span></p> 
@snapend

Note:
One example on how to update silicon policy is shown here


Code is in: 
- KabylakeOpenBoardPkg/FspWrapper/Library/PeiFspPolicyUpdateLib/PeiSaPolicyUpdatePreMem.c

  //
  // If SpdAddressTable are not all 0, it means DIMM slots implemented and
  // MemorySpdPtr* already updated by reading SPD from DIMM in SiliconPolicyInitPreMem.
  //
  // If SpdAddressTable all 0, this is memory down design and hardcoded SpdData
  // should be applied to MemorySpdPtr*.

---
@title[Dynamically set Defaults ]
<p align="right"><span class="gold" >@size[1.1](<b>Dynamically set Defaults</b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[west span-100 ]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-100 ]
<p style="line-height:70%" align="left" ><span style="font-size:0.75em;" ><br><br>
The Default Store PCD is also a dynamic PCD. <br><br>
During boot, the board initialization code checks the boot mode and selects the default store.  <br><br>
This step must be after SetSku. Otherwise, the default setting may be wrong.
</span></p>
@snapend

@snap[west span-100 ]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:35% " align="left"></span><span style="font-size:0.4em; font-family:Consolas;" ><br>&nbsp;
. &nbsp;. &nbsp;.<br>&nbsp;
if (NeedDefaultConfig()) &lbrace; <br>&nbsp;
PcdSet16S (@color[yellow](PcdSetNvStoreDefaultId), 0x0); <br>&nbsp;
&rbrace; <br>&nbsp;
</span></p>
@snapend



Note:

---?image=assets/images/slides/Slide43.JPG
@title[Board Porting ]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>Board Porting</b>)</span><span style="font-size:0.8em;" ></span></p>

@snap[south-east span-33 ]
<br>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >GPIO </span> </li>
  <li><span style="font-size:0.65em" >SIO </span> </li>
  <li><span style="font-size:0.65em" >ACPI </span> </li>
</ul>
<br>
<br>
<br>
<br>
@snapend

Note:


Porting. Where are the modules to be ported for a new board? 

Board Specific initialization 



---?image=assets/images/slides/Slide_TableDHote.JPG
@title[Staged Approach by Features]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)</span><br><span style="font-size:0.75em;" >- Platform Firmware Boot Stage PCD</span></p>
@snap[north-west span-70 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >PCD Variable:<br></span>
<span style="font-size:0.5em; font-family:Consolas;">
gPlatformModuleTokenSpaceGuid.PcdBootStage
</span></p>
@snapend

@snap[north-west span-50 ]
<br>
<br>
<br>
<br>
<table id="recTable">
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 1&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Enable Debug &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 2&nbsp;</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Memory Initialization</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 3&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Boot to UEFI Shell only &nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 4&nbsp;</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Boot ot OS</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 5&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Boot ot OS w/ Security enabled&nbsp;</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 6&nbsp;</span></p></td>
		<td bgcolor="#323232"><p style="line-height:10%"><span style="font-size:0.56em" >Advanced Feature Selection</span></p></td>
	</tr>
	<tr>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Stage 7&nbsp;</span></p></td>
		<td bgcolor="#121212"><p style="line-height:10%"><span style="font-size:0.56em" >Performance Opetimizations &nbsp;</span></p></td>
	</tr>
</table>
<br>
@snapend


@snap[south-east span-45 ]
<p style="line-height:50%" align="left" ><span style="font-size:0.6em;" >
PCD Is tested within .FDF to see which modules to include 
</span></p>
@snapend

Note:
table d’hôte  Pronounced "Tab la dout"
Image source: http://3.bp.blogspot.com/-nCzQh7Xu3_I/Uzk1a4DRk-I/AAAAAAAABCY/lQvT1cbn8Ug/s1600/5892-Caucasian-Man-Sitting-At-A-Table-And-Reading-A-Menu-At-A-Restaurant-Clipart-Illustration.jpg



Depending on the stage # provides some idea regarding what components are needed for a BIOS solution. It can be 3M full featured BIOS, or only 256K if just the basic boot is required, in some cases. 

This work can be done by defining some default configuration in PlatformConfig.dsc. 
For example, PcdBootStage|4 can be used to configure a BIOS to support a boot to OS (with ACPI/SMM), or PcdBootStage|3 to configure a BIOS to boot to shell only (without ACPI/SMM) 

- Stage I - Minimal Debug
  - Serial Port, Port 80, External debuggers Optional: Software debugger
- Stage II  - Memory Functional
  - Basic hardware initialization including main memory
- Stage III - Boot to UEFI Shell
   - Generic DXE driver execution
- Stage IV - Boot to OS
  - Boot a general purpose operating system with the minimally required feature set. Publish a minimal set of ACPI tables.- Stage V -Security Enabled
  - UEFI Secure Boot, TCG trusted boot, DMA protection, etc.
- Stage VI - Advanced Feature Selection
  - Firmware update, power management, networking support, manageability, testability, reliability, availability, serviceability, non-essential provisioning and resiliency mechanisms
- Stage VII – Tuning
   - Size and performance optimizations

Within the DSC and  FDF choose which modules to include based on PCD
Example
<pre>
DSC:
[PcdsFeatureFlag]
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdStopAfterMemInit|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdUefiSecureBootEnable|FALSE
  gMinPlatformPkgTokenSpaceGuid.PcdTpm2Enable|FALSE

!if gMinPlatformPkgTokenSpaceGuid.PcdBootStage >= 1
 gMinPlatformPkgTokenSpaceGuid.PcdStopAfterDebugInit|TRUE
!endif

Example FDF
!if gMinPlatformPkgTokenSpaceGuid.PcdBootToShellOnly == FALSE
INF  MdeModulePkg/Universal/FaultTolerantWriteDxe/FaultTolerantWriteSmm.inf
INF  MdeModulePkg/Universal/Variable/RuntimeDxe/VariableSmmRuntimeDxe.inf
INF  MdeModulePkg/Universal/Variable/RuntimeDxe/VariableSmm.inf
!endif
</pre>


---?image=assets/images/slides/Slide45.JPG
<!-- .slide: data-transition="none" -->
@title[Stages vs. Boot Flow]
<p align="right"><span class="gold" >@size[1.1](<b>Stages vs. Boot Flow</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:

1. enable debug
2. memory initialization
3. boot to UEFI shell only
4. boot to OS
5. boot to OS w/ security enabled
6. Advanced Feature Selection
7. Not shown  Performance Optimizations



+++?image=assets/images/slides/Slide46.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stages vs. Boot Flow 02]
<p align="right"><span class="gold" >@size[1.1](<b>Stages vs. Boot Flow</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:
1. enable debug
2. memory initialization
3. boot to UEFI shell only
4. boot to OS
5. boot to OS w/ security enabled
6. Advanced Feature Selection
7. Not shown  Performance Optimizations


+++?image=assets/images/slides/Slide47.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stages vs. Boot Flow 03]
<p align="right"><span class="gold" >@size[1.1](<b>Stages vs. Boot Flow</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:
1. enable debug
2. memory initialization
3. boot to UEFI shell only
4. boot to OS
5. boot to OS w/ security enabled
6. Advanced Feature Selection
7. Not shown  Performance Optimizations


+++?image=assets/images/slides/Slide47_1.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stages vs. Boot Flow 04]
<p align="right"><span class="gold" >@size[1.1](<b>Stages vs. Boot Flow</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:
1. enable debug
2. memory initialization
3. boot to UEFI shell only
4. boot to OS
5. boot to OS w/ security enabled
6. Advanced Feature Selection
7. Not shown  Performance Optimizations

+++?image=assets/images/slides/Slide48.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stages vs. Boot Flow 05]
<p align="right"><span class="gold" >@size[1.1](<b>Stages vs. Boot Flow</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:
1. enable debug
2. memory initialization
3. boot to UEFI shell only
4. boot to OS
5. boot to OS w/ security enabled
6. Advanced Feature Selection
7. Not shown  Performance Optimizations

+++?image=assets/images/slides/Slide49.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stages vs. Boot Flow 06]
<p align="right"><span class="gold" >@size[1.1](<b>Stages vs. Boot Flow</b>)</span><span style="font-size:0.75em;" ></span></p>

Note:
1. enable debug
2. memory initialization
3. boot to UEFI shell only
4. boot to OS
5. boot to OS w/ security enabled
6. Advanced Feature Selection
7. Not shown  Performance Optimizations

---?image=assets/images/slides/Slide50.JPG
@title[Staged Approach by Features]
<p align="right"><span class="gold" >@size[1.1](<b>Staged Approach by Features</b>)<br></span><span style="font-size:0.75em;" >- Firmware Volume</span></p>

@snap[north-east span-60 ]
<br>
<br><br>
<br><br>
<p style="line-height:80%" align="left" ><span style="font-size:0.9em;" >
Modules organized by Firmware Volumes according to the different boot stages
</span>
<span style="font-size:0.5em; font-family:Consolas;">
</span></p>
@snapend


Note:

HOW is it implemented??

In order to separate modules in different boot stages, the BKM is to Standardize the firmware layout using Firmware Volumes according to the different boot stages


---?image=assets/images/slides/Slide51.JPG
@title[UEFI Firmware Volumes (FV) - Review]
<p align="right"><span class="gold" >@size[1.1](<b>UEFI Firmware Volumes (FV) - Review</b>)<br></span><span style="font-size:0.75em;" ></span></p>

@snap[north-west span-70 ]
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.8em;" >
<br>
Platform Initialization - Firmware Volume 
</span></p>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.75em" >Basic storage repository for data and code is the Firmware Volume (FV)  </span> </li>
  <li><span style="font-size:0.75em" >Each FV is organized into a file system, each with attributes </span> </li>
  <li><span style="font-size:0.75em" >One or more Firmware File Sections (FFS) files are combined into a FV  </span> </li>
  <li><span style="font-size:0.75em" >Flash Device may contain one or more FVs </span> </li>
  <li><span style="font-size:0.75em" >.FDF file controls the layout → .FD image(s) </span> </li>
</ul>
<br>
<br>
<p style="line-height:70%" align="left" ><span style="font-size:0.65em;" >
<a href="https://uefi.org/specifications"> PI Spec Vol. 3</a>
</span></p>

@snapend


Note:
In order to separate modules in different boot stage, we standardize the firmware layout. 
First review of EDK II – UEFI Firmware Volumes
Platform Initialization - Firmware Volume 

- Basic storage repository for data and code is the Firmware Volume (FV) 
- Each FV is organized into a file system, each with attributes
- One or more Firmware File Sections (FFS) files are combined into a FV 
- Flash Device may contain one or more FVs.
- .FDF file controls the layout 



- FvPreMemory – The PEIM dispatched before the memory initialization. 
- FvPostMemory – The PEIM dispatched after the memory initialization. 
- FvUefiBoot – The DXE driver supporting UEFI boot, such as boo to UEFI shell. 
- FvOsBoot – The DXE driver supporting UEFI OS boot, such as UEFI Windows. 
- FvSecurity – The security related modules, such as UEFI Secure boot, TPM etc. 
- FvAdvanced – The advanced feature modules, such as UEFI network, IPMI etc. 



---
@title[Standardize FV By Stages]
<p align="right"><span class="gold" >@size[1.1](<b>Standardize FV By Stages</b>)</span></span></p>


@snap[north-east span-71 ]
<p style="line-height:20%"><br><br><br>&nbsp;</p>

@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>&nbsp; </b><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>&nbsp; </b><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>&nbsp; </b><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>&nbsp; </b><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>&nbsp; </b><br>&nbsp;</span></p>)
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>&nbsp; </b><br>&nbsp;</span></p>)
@snapend



@snap[north-west span-30 ]
<p style="line-height:20%"><br><br><br>&nbsp;</p>

@box[bg-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>Pre-Memory </b><br>&nbsp;</span></p>)
@box[bg-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>Post-Memory  </b><br>&nbsp;</span></p>)
@box[bg-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>UEFI Boot </b><br>&nbsp;</span></p>)
@box[bg-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>OS Boot </b><br>&nbsp;</span></p>)
@box[bg-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>Security </b><br>&nbsp;</span></p>)
@box[bg-blue-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.7em;" ><b>Advanced </b><br>&nbsp;</span></p>)
@snapend




@snap[north-east span-65 fragment ]
<p style="line-height:20%"><br><br><br><br>&nbsp;</p>
<p style="line-height:32%" align="left"><span style="font-size:0.5em;" ><b>@color[yellow](FvPreMemory) </b>– The PEIM dispatched before the memory initialization. Also included @color[yellow](FSP - FVs) 
<br><br>&nbsp;</span></p>
<p style="line-height:32%" align="left"><span style="font-size:0.5em;" ><b>@color[yellow](FvPostMemory)</b> – The PEIM dispatched after the memory initialization. Also included @color[yellow](FSP - FVs)
<br><br>&nbsp;</span></p>
<p style="line-height:32%" align="left"><span style="font-size:0.5em;" ><b>@color[yellow](FvUefiBoot)</b> – The DXE driver supporting UEFI boot, such as boot to UEFI shell. 
<br><br>&nbsp;</span></p>
<p style="line-height:32%" align="left"><span style="font-size:0.5em;" ><b>@color[yellow](FvOsBoot)</b> – The DXE driver supporting UEFI OS boot, such as UEFI Windows
<br><br>&nbsp;</span></p>
<p style="line-height:32%" align="left"><span style="font-size:0.5em;" ><b>@color[yellow](FvSecurity)</b> – The security related modules, such as UEFI Secure boot, TPM etc. 
<br><br>&nbsp;</span></p>
<p style="line-height:32%" align="left"><span style="font-size:0.5em;" ><b>@color[yellow](FvAdvanced) </b>– The advanced feature modules, such as UEFI network, IPMI etc 
<br>&nbsp;</span></p>
@snapend



Note:

In order to separate modules in different boot stage, BKM to Standardize the firmware layout. 

- FvPreMemory – The PEIM dispatched before the memory initialization. 
- FvPostMemory – The PEIM dispatched after the memory initialization. 
- FvUefiBoot – The DXE driver supporting UEFI boot, such as boo to UEFI shell. 
- FvOsBoot – The DXE driver supporting UEFI OS boot, such as UEFI Windows. 
- FvSecurity – The security related modules, such as UEFI Secure boot, TPM etc. 
- FvAdvanced – The advanced feature modules, such as UEFI network, IPMI etc. 

---
@title[FSP Firmware Volumes ]
<p align="right"><span class="gold" >@size[1.1](<b>FSP Firmware Volumes </b>)<br></span><span style="font-size:0.75em;" >- Created Pre-Build</span></p>

@snap[north-west span-49 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-48 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.75em; ">
@color[#A8ff60](Fsp.fd) Rebased for FVs

</span></p>
@snapend



@snap[north span-29 fragment ]
<br>
<br>
<br>
<br>
@box[bg-green-pp text-black rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>FvFspT</b><br><br>&nbsp;</span></p>)
@box[bg-green-pp text-black rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>FvFspM</b><br><br>&nbsp;</span></p>)
@box[bg-green-pp text-black rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em;" ><b>FvFspS</b><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-35 fragment]
<br>
<br>
<br>
<br>
<br>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:20%" align="left"><span style="font-size:0.45em;" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Temp Memory<br>&nbsp;</span></p>)
<p style="line-height:20%"><br>&nbsp;</p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:20%" align="left"><span style="font-size:0.45em;" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- -&gt;FvPreMemorySilicon<br>&nbsp;</span></p>)
<p style="line-height:20%"><br>&nbsp;</p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:20%" align="left"><span style="font-size:0.45em;" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- -&gt;FvPostMemorySilicon<br>&nbsp;</span></p>)
@snapend


@snap[north-west span-60 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
&nbsp;MyWorkSpace/<br>&nbsp;&nbsp;
@color[yellow](edk2)/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  - "@color[#FFC000](<font face="Arial">edk2 Common</font>)"<br>&nbsp;&nbsp;
@color[yellow](edk2-platforms)/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Platform/ "@color[#FFC000](<font face="Arial">Platform</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/MinPlatformPkg<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       include/  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          @color[#A8ff60](flashmapinclude.fdf) <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          BoardXPkg/ "@color[#FFC000](<font face="Arial">Board</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/ "@color[#FFC000](<font face="Arial">Silicon</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
       MinPlatformPkg/<br>&nbsp;&nbsp;
@color[yellow](edk2-non-osi)/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Silicon/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Intel/<br>&nbsp;&nbsp;
@color[yellow](FSP)/"@color[#FFC000](<font face="Arial">Silicon</font>)"<br>&nbsp;&nbsp;&nbsp;&nbsp;
   BoardXPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
   @color[#A8ff60](<b>Fsp.fd</b>)
</span></p>
@snapend

@snap[south-east span-40 ]
<p style="line-height:40%" align="left" ><span style="font-size:0.5em; ">
Pre-Build w/ <b>`RebaseAndPatchFspBinBaseAddress.py `</b>
</span></p>
<br>
@snapend


Note:

Prior to the EDK II build the Tool RebaseAndPatchFspBinBaseAddress.py will rebase the Fsp.Fd using the board Flashmapinclude.fdf file into 3 FVs

- FvFspT
– Temp Memory
- FvFspM
-> FvPreMemorySilicon
- FvFspS
-> FvPostMemorySilicon


---?image=assets/images/slides/Slide54.JPG
@title[FSP APIs in FSP Binary]
<p align="right"><span class="gold" >@size[1.1](<b>FSP APIs in FSP Binary</b>)<br></span><span style="font-size:0.5em;" >Using Intel<sup>&reg;</sup> FSP w/ EDK II: 
<a href="https://firmware.intel.com/sites/default/files/A_Tour_Beyond_BIOS_Using_the_Intel_Firmware_Support_Package_with_the_EFI_Developer_Kit_II_(FSP2.0).pdf">PDF</a>
</span></p>

Note:
Despite the variability of the FSP binaries, the FSP API caller (aka FSP consumer) could be a generic module to invoke the 5 APIs defined in FSP EAS (External Architecture Specification) to finish silicon initialization. 
5 APIs are:
  TempRamInit, NotifyPhase, FspMemoryInit, TempRamExit, FspSiliconInit 
 
The flow on this slide describes the FSP, with the FSP binary from the "FSP Producer" in green and the platform code that integrates the binary, or the "FSP Consumer", in blue 


The FSP EAS describes the API interface to the FSP binary that the consumer code will 
invoke, and it also describes the hand off state from the execution of the FSP binary. The latter information is conveyed in Hand-Off Blocks, or HOB’s. The FSP uses many of the data structures defined in the PI Specification including HOBs, Firmware Volumes, Firmware Files, etc. 
The FSP binary can be integrated into any firmware solution, such as UEFI firmware (EDK II)

1. Bootloader provided SEC phase starts executing from Reset Vector 
	a) Switches the mode to 32-bit mode. 
	b) Initializes the early platform as needed. 
	c) Finds FSP-T and calls the TempRamInit() API. The bootloader also has the option to initialize the temporary memory directly, in which case this step and step 2 are skipped. 
2. FSP initializes temporary memory and returns from TempRamInit() API. 
3. Bootloader initializes the stack in temporary memory. 
	a) Initializes the platform as needed. 
	b) Finds FSP-M and calls the FspMemoryInit() API. 
4. FSP initializes memory and returns from FspMemoryInit() API. 
5. Bootloader relocates itself to Memory. 
6. Bootloader calls TempRamExit() API. If Bootloader initialized the temporary memory in step 1.c)… this step and the next step are skipped. 
7. FSP returns from TempRamExit() API. 
8. Bootloader finds FSP-S and calls FspSiliconInit() API. 
9. FSP returns from FspSiliconInit() API. 
10. Bootloader continues and device enumeration. 

11. Bootloader calls NotifyPhase() API with AfterPciEnumeration parameter. 
12. Bootloader calls NotifyPhase() API with ReadyToBoot parameter before transferring control to OS loader. 
13. When booting to a non-UEFI OS, Bootloader calls NotifyPhase() API with EndOfFirmware parameter immediately after ReadyToBoot. 
14. When booting to a UEFI OS, Bootloader calls NotifyPhase() with EndOfFirmware parameter during ExitBootServices. 
Another Note: : If FSP returns the reset required status in any of the API, then bootloader performs the reset. Refer to the Integration Guide for more details on Reset Types. 


---?image=assets/images/slides/Slide55.JPG
@title[Boot Flow with FSP API Mode]
<p align="right"><span class="gold" >@size[1.1](<b>Boot Flow with FSP API Mode</b>)</span><span style="font-size:0.5em;" ></span></p>

<p style="line-height:40%" align="left" ><span style="font-size:0.75em; ">
5 APIs for FSP
</span></p>

@snap[south-west span-40 ]
<p style="line-height:40%" align="left" ><span style="font-size:0.5em;" >Using Intel<sup>&reg;</sup> FSP w/ EDK II: 
<a href="https://firmware.intel.com/sites/default/files/A_Tour_Beyond_BIOS_Using_the_Intel_Firmware_Support_Package_with_the_EFI_Developer_Kit_II_(FSP2.0).pdf">PDF</a>
</span></p>
@snapend

Note:

The normal boot flow of FSP2.0 is shown on this slide. In normal boot, the SecPlatformLib (sample at https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/Library/SecFspWrapperPlatformSecLibSample ), which is linked by the SecCore (https://github.com/tianocore/edk2/tree/master/UefiCpuPkg/SecCore ), calls first FSP API – TempRamInitApi, and then transfers the control to the PeiCore. SecPlatformLib also registers SecTempRamDonePpi (https://github.com/tianocore/edk2/blob/master/IntelFsp2WrapperPkg/Library/SecFspWrapperPlatformSecLibSample/SecTempRamDone.c ) for TempRamExitApi. 

One platform PEIM is responsible to detect the current boot mode and finds some variables (like capsule variable) to finalize the boot mode selection. The FspmWrapperPeim (https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/FspmWrapperPeim ) has a dependency on MasterBootModePpi, so after the boot mode is determined, the FspmWrapperPeim is invoked. FspmWrapperPeim gets the UPD data, allocates buffer for UPD override data, then calls UpdateFspmUpdData() to update the UPD data according to platform policy (sample at https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/Library/BaseFspWrapperPlatformLibSample ). Then FspmWrapperPeim calls second FSP API – FspMemoryInitApi. Once this API returns, FspmWrapperPeim calls PostFspmHobProcess() to process the initial FSP HOB. (sample at https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/Library/PeiFspWrapperHobProcessLibSample ). FspWrapperHobProcessLib parses resource HOB and installs PEI memory to PEI core. 

Once the PeiCore gets permanent memory, PeiCore does TemporaryRam migration and calls PeiTemporaryRamDonePpi, where TempRamExitApi is called. After that, PeiCore installs PeiMemoryDiscovered. Then the dependency of FspsWrapperPeim (https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/FspsWrapperPeim ) is satisfied. FspsWrapperPeim gets the UPD data, allocates buffer for UPD override data, then calls UpdateFspsUpdData() to update the UPD data according to platform policy. (sample at https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/Library/BaseFspWrapperPlatformLibSample ). Then FspsWrapperPeim calls FspSiliconInitApi to finish final silicon initialization. Once this API returns, FspsWrapperPeim calls PostFspsHobProcess() to process FSP HOB after silicon initialization. (sample at https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/Library/PeiFspWrapperHobProcessLibSample ). Typically, there will be more data in the FSP HOB at this time. Most work in PostFspsHobProcess() is to migrate the HOB data from FSP to FspWrapper. 

Then the PeiCore will continue dispatching the final PEIMs and jump into the DxeCore. Then the DxeCore launches FspWrapperNotifyDxe (https://github.com/tianocore/edk2/tree/master/IntelFsp2WrapperPkg/FspWrapperNotifyDxe ). FspWrapperNotifyDxe registers a callback function for the last FSP API – FspNotifyApi, for AfterPciEnumeration, ReadyToBoot, and EndOfFirmware. 

---?image=assets/images/slides/Slide56.JPG
@title[FSP 2.1 Dispatch Mode Boot Flow]
<p align="right"><span class="gold" >@size[1.1](<b>FSP 2.1 Dispatch Mode Boot Flow</b>)</span><span style="font-size:0.5em;" ></span></p>

<p style="line-height:40%" align="left" ><span style="font-size:0.5em; ">
<b>`gIntelFsp2WrapperTokenSpaceGuid`.@color[yellow](`PcdFspModeSelection`)</b>	0 - dispatch, 1 – API
</span></p>

@snap[south-west span-40 ]
<p style="line-height:40%" align="left" ><span style="font-size:0.6em; ">
<a href="https://www.intel.com/FSP">FSP Spec 2.1</a>
</span></p>
@snapend

Note:

FSP 2.1 introduces Dispatch Mode Boot Flow

The Pcd - gIntelFsp2WrapperTokenSpaceGuid.PcdFspModeSelection	0 - dispatch, 1 – API (default)  is used

Dispatch mode is an optional boot flow intended to enable FSP to integrate well in to UEFI bootloader implementations. Implementation of this boot flow necesitates that the underlying FSP implementation uses the Pre-EFI Initialization (PEI) environment defined in the PI Specification. 

Blue blocks are from the FSP binary and green blocks are from the bootloader. Blocks with mixed colors indicate that both bootloader and FSP modules are dispatched during that phase of the boot flow. 
Dispatch mode is intended to implement a boot flow that is as close to a standard UEFI boot flow as possible. In dispatch mode, FSP exposes Firmware Volumes (FV) directly to the bootloader. The PEIM in these FV are executed directly in the context of the PEI environment provided by the bootloader. FSP-T, FSP-M, and FSP-S could contain one or multiple FVs. The exact FVs layout will be described in the Integration Guide. In dispatch mode, the PPI database, PCD database, and HOB list are shared between the bootloader and the FSP. 
In dispatch mode, the NotifyPhase() API API is not used. Instead, FSP-S contains DXE drivers that implement the native callbacks on equivalent events for each of the NotifyPhase() invocations. 


---?image=assets/images/slides/Slide57.JPG
@title[ Platform Hooks Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Platform Hooks</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Using EDK II Libraries</span>


@snap[south-east span-25 fragment]
![how](/assets/images/How_text.png)
<br>
<br>
<br>
@snapend

Note:

How? – by using EDK II Libraries for Platform Hooks


---?image=assets/images/slides/Slide58.JPG
@title[EDK II Libraries w/ Platform Hooks]
<p align="right"><span class="gold" >@size[1.1](<b>EDK II Libraries w/ Platform Hooks </b>)</span><span style="font-size:0.75em;" ></span></p>



@snap[north-east span-80 fragment ]
<br>
<br>
<br>
<br>
<p style="line-height:75%" align="left"><span style="font-size:0.9em">@color[yellow](DSC maps library class to library-instances)</span></p>
<br>
@snapend


@snap[north-east span-80 fragment ]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:70%" align="left"><span style="font-size:0.9em">Syntax in DSC File</span><br>
<span style="font-size:0.55em; font-family:Consolas;">
&nbsp;&nbsp;[libraryclasses] <br>
&nbsp;&nbsp;LibraryClassName|Path/To/@color[cyan](LibInstanceNameInstance1).inf  </span> </p>  
<br>
@snapend


@snap[south span-85 fragment ]
@box[bg-purple-pp text-white rounded   my-box-pad2 ](<span style="font-size:01.0em" >Search INF files for string:&nbsp;&nbsp; "<b>`LIBRARY_CLASS  =`</b>"<br>&nbsp;</span>)
<br>
@snapend


Note:

DSC maps library-class to library-instances
Global, by type, individual override
Effected by size, speed, built in, binary distribution 
PCI example
PciCfg – Protocol function call by GUID (PEI)
PciRootBridgeIo – Protocol function call by GUID (DXE)
Syntax in DSC file
	[libraryclasses] 
	LibraryClassName|Path/To/LibInstanceNameInstance1.inf
	
	
also note, Workspace relative paths!

Check for existing library instances.

Search INF for string: LIBRARY_CLASS  =


---?image=assets/images/slides/Slide59.JPG
@title[Library Classes Section in DSC]
<p align="right"><span class="gold" >@size[1.1](<b>Library Classes Section in DSC </b>)</span><span style="font-size:0.75em;" ></span></p>

<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" >`DebugLib` class example </span></p>
<br>
```
 [LibraryClasses]
     DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
     • • •
 [LibraryClasses.common.DXE_CORE]
         • • •
    DebugLib|IntelFrameworkModulePkg/Library/PeiDxeDebugLibReportStatusCode/
           PeiDxeDebugLibReportStatusCode.inf  
        • • •
 [LibraryClasses.common.DXE_SMM_DRIVER]
    DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

```
<hr>
```
 [Components]
      • • •
 MyPath/MyModule.inf {
  <LibraryClasses>
    DebugLib|MdePkg/Library/BaseDebugLibSerialPort.inf
 }
 
``` 


@snap[north-east span-35 fragment ]
<br>
<br>
<br>
<br>
@box[bg-purple-pp text-white my-box-pad2  ](<span style="font-size:0.75em;"><b> Library Class Section</b></span>)
<br>
<br>
<br>
<br>
<br>
@box[bg-green-pp text-white my-box-pad2  ](<span style="font-size:0.75em;"><b> Components Section</b></span>)
@snapend

Note:

This is an example!!!

Build the slide with each libraryclass


Library instances selected in the DSC help with porting

Only one instance of each named library class may be linked to a given module

---
@title[Platform Initialization Board hook Modules]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board hook Modules</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-40 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-58 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-12 ]
<br>
![hook](/assets/images/hook.png)
@snapend

@snap[north-west span-60 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
<br>&nbsp;&nbsp;
MinPlatformPkg/<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Include/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	   @color[yellow](BoardnitLib.h)<br>&nbsp;&nbsp;&nbsp;&nbsp;
  Library/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  . . .<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
  @color[yellow](PlatformInit)/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  PlatformInitPreMem/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  PlatformInitPostMem/<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitDxe/<br><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitSmm/  <br>&nbsp;&nbsp;&nbsp;&nbsp;
</span></p>
@snapend

@snap[north-east span-55 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
<br>
BoardDetect()<br>
BoardDebugInit()<br>
BoardBootModeDetect()<br>
BoardInitBeforeMemoryInit()<br>
BoardInitBeforeTempRamExit()<br>
BoardInitAfterTempRamExit()<br>
BoardInitAfterMemoryInit()<br>
BoardInitBeforeSiliconInit()<br>
<br><br><br><br>
BoardInitAfterPciEnumeration()<br>
BoardInitReadyToBoot()<br>
BoardInitEndOfFirmware()<br>
</span></p>
@snapend


@snap[north-east span-18 fragment]
<br><br><br><br><br>
<p style="line-height:70%" ><span style="font-size:01.1em; font-weight: bold;" >@color[yellow](PEI)</span></p>
<p style="line-height:40%" ><span style="font-size:0.9em; font-weight: bold;" ><br><br><br><br><br><br><br><br>&nbsp;</span></p>
<p style="line-height:70%" ><span style="font-size:01.1em; font-weight: bold;" >@color[yellow](DXE)</span></p>
@snapend




Note:

The PlatformInit folder (Intel/MinPlatformPkg/PlatformInit) - PlatformInitPei, PlatformInitDxe and PlatformInitSmm control the platform initialization flow. Because this flow needs to involve the board initialization,  there is a set of  board hook points defined in BoardInitLib (MinPlatformPkg/Include/Library/BoardInitLib.h) 

---
@title[Platform Initialization Board hook Modules]
<p align="right"><span class="gold" >@size[1.1](<b>Platform Initialization Board hook Modules</b>)</span><span style="font-size:0.75em;" ></span></p>


@snap[north-west span-40 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-east span-58 ]
<br>
<br>
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@box[bg-black text-white rounded my-box-pad2  ](<p style="line-height:60% "><span style="font-size:0.9em;" ><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-east span-12 ]
<br>
![hook](/assets/images/hook.png)
@snapend


@snap[north-west span-60 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
<br>&nbsp;&nbsp;
MinPlatformPkg/<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
  . . .<br><br>&nbsp;&nbsp;&nbsp;&nbsp;
  PlatformInit/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    PlatformInitPei/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  @color[yellow](PlatformInitPreMem)/
	  <br><br><br><br>
	  <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
	  @color[yellow](PlatformInitPostMem)/
</span></p>
@snapend

@snap[north-east span-55 ]
<br>
<br>
<p style="line-height:50%" align="left" ><span style="font-size:0.5em; font-family:Consolas;">
<br>
@color[yellow](PlatformInitPreMem)/<br>&nbsp;&nbsp;
BoardDetect()<br>&nbsp;&nbsp;
BoardDebugInit()<br>&nbsp;&nbsp;
BoardBootModeDetect()<br>&nbsp;&nbsp;
BoardInitBeforeMemoryInit()<br>&nbsp;&nbsp;
. . . <br><br>&nbsp;&nbsp;
<font face="Arial">Notify call back </font><br>&nbsp;&nbsp;
BoardInitAfterMemoryInit()
<br><br><br><br><br>
@color[yellow](PlatformInitPostMem)/<br>&nbsp;&nbsp;

BoardInitBeforeSiliconInit()<br>&nbsp;&nbsp;
. . . <br>&nbsp;&nbsp;
BoardInitAfterSiliconInit()<br>
</span></p>
@snapend


@snap[north-east span-18 fragment]
<br><br><br><br><br><br><br><br>
<p style="line-height:70%" ><span style="font-size:01.1em; font-weight: bold;" ><br><br><br>@color[yellow](PEI)</span></p>

@snapend




Note:

The PlatformInit folder (Intel/MinPlatformPkg/PlatformInit) - PlatformInitPei, PlatformInitDxe and PlatformInitSmm control the platform initialization flow. Because this flow needs to involve the board initialization,  there is a set of  board hook points defined in BoardInitLib (MinPlatformPkg/Include/Library/BoardInitLib.h) 



---?image=assets/images/slides/Slide5.JPG
@title[EDK II Open Platform Summary Section]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>EDK II Open Platform <br>Summary</b>)</span></span></p>

@snap[north-east span-35 ]
<br>
<br>

<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Minimal /Full BIOS </span> </li>
  <li><span style="font-size:0.65em" >Feature ON/OFF </span> </li>
  <li><span style="font-size:0.65em" >Smbios/TPM/SecureBoot/ </span> </li>
  <li><span style="font-size:0.65em" >. . . </span> </li>
</ul>
@snapend

@snap[south-west span-30]
<br>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >Setup Variable</span> </li>
  <li><span style="font-size:0.65em" >PCD </span> </li>
  <li><span style="font-size:0.65em" >Policy Hob/PPI/Protocol </span> </li>
</ul>
<br>
<br>
<br>
@snapend

@snap[south-east span-33 ]
<br>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.65em" >GPIO </span> </li>
  <li><span style="font-size:0.65em" >SIO </span> </li>
  <li><span style="font-size:0.65em" >ACPI </span> </li>
</ul>
<br>
<br>
<br>
<br>
@snapend



Note:
In order to provide suggestions on the problem statements earilier, we need to focus on the following four areas: 

- Feature. How does a BIOS provide the feature selection option to a developer? 
- Configuration. From which interface can a platform module get the configuration data? 
- Porting. Where are the modules to be ported for a new board? 
- Tree Structure. What does an EDKII platform package look like? 

---  
@title[summary]
<BR>
### <p align="center"<span class="gold"   >Summary </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Explain the EDK II Open board platforms <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;infrastructure  & focus areas</span> </li>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Describe Intel® FSP with  the EDK II Open board<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;platforms </span></li>
</ul>



---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG) 

---
@title[return to main]
<p align="center"><span class="gold"   >@size[1.2em](<b>Return to Main Training Page</b>)</span></p>
<br>
<br>
<br>
<br>
<br>
<p align="center"><span style="font-size:0.9em">Return to Training Table of contents for next presentation <a href="https://github.com/tianocore-training/Tianocore_Training_Contents/wiki#schedule--outline">link</a></span></p>

@snap[north span-30 ]
<br>
<br>
<br>
<a href="https://github.com/tianocore-training/Tianocore_Training_Contents/wiki#schedule--outline">
![trainingLogo](/assets/images/returnTrainingLogo.png)</a>
@snapend


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2019, Intel Corporation. All rights reserved.
**/

```
