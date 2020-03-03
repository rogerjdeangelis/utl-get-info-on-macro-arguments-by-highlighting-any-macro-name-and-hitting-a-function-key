# utl-get-info-on-macro-arguments-by-highlighting-any-macro-name-and-hitting-a-function-key
Get info on macro arguments by highlighting any macro name and hitting a function key

    SAS Forum:

    Get info on macro arguments by highlighting any macro name and hitting a function key

    github
    https://tinyurl.com/udo7qfb
    https://github.com/rogerjdeangelis/utl-get-info-on-macro-arguments-by-highlighting-any-macro-name-and-hitting-a-function-key


    For other subsequently removed 1980s editor functionality see;
    https://tinyurl.com/y74wdoya
    https://github.com/rogerjdeangelis?utf8=%E2%9C%93&tab=repositories&q=classic+in%3Aname&type=&language=

    related to SAS Forum
    https://tinyurl.com/vvqgd63
    https://communities.sas.com/t5/SAS-Enterprise-Guide/Formatting-Macro-Parameter-Comments/m-p/629126

    AS A LARK

      Put this on any function key
      %macro cuth/cmd;%local i;%do i=1 %to 12; c '  ' ' ' all;%end;%mend; %cuth;

      Highlight some badly spaced text and hit the function key.
      You can also type cuth on the command line ot mouse action.


    This requires the classic SAS editor. The one with line prefix area. ie SAS on the 1980s.
    This will not workin any subsequent SAS enhanced editors due to reduced functinality.

     METHOD ( THIS WORKS WITH ANY MACRO)

         1. Your need information on the macro in your editor

         Command ===>

         00001 %macro doit(
         00002     date=3/3/2010
         00003    ,height=72
         00004    ,weight=165
         00005    ) / des="select students";
         00006
         00007   %put &=date;
         00008   %put &=height;
         00009   %put &=weight;
         00010
         00011 %mend doit;

         2. Highlight the macro name "doit"

         3. Hit function key 1

         4. A window will pop up with this info

            Sample Arguments for macro doit

             Date=mm/dd/yyy : Date of Birth
             Height=72      : Height in Inches
             Weight=165     : Weight in Lbs

    *         _
     ___  ___| |_ _   _ _ __
    / __|/ _ \ __| | | | '_ \
    \__ \  __/ |_| |_| | |_) |
    |___/\___|\__|\__,_| .__/
                       |_|
    ;

    options sasautos=("c:/oto"); /* network autocall) */

    * you need the macro in the classic editor;

    %macro doit(
        date=3/3/2010
       ,height=72
       ,weight=165
       ) / des="select students";

      %put &=date;
      %put &=height;
      %put &=weight;

    %mend doit;

    * macro to create pop up window;
    * save this macro in your sasautos (autocall library);
    * you need to do this any macro you wish to document yhrh arguments;

    filename ft15f001 "c:/oto/doitx.sas";
    parmcards4;
    %macro doitx(arg);
      %window form

         #3 @5 "Sample Arguments for macro &arg' color=blue
         #6 @5 'Date=mm/dd/yyy : Date of Birth'        //
            @5 'Height=72      : Height in Inches'  //
            @5 'Weight=165     : Weight in Lbs'     color=black +2 outpath 50 color=green required=yes
    ;
    %display form;
    %mend doitx;
    ;;;;
    run;quit;

    * set finction key 1 PF1;
    On function key 1;

    note;notesuubmit "%macarg";

    *
     _ __  _ __ ___   ___ ___  ___ ___
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
    ;

       highlight doit and hit pf1


    *            _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| '_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    ;

     Sample Arguments for macro doit

      Date=mm/dd/yyy : Date of Birth
      Height=72      : Height in Inches
      Weight=165     : Weight in Lbs


