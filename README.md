# utl_dm_command_to_open_last_dataset_in_rwork_library
DM command to open last dataset in rwork library. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.

    DM command to open last dataset in rwork library

    Here is how you can do it using command macros and a seven button mouse

    github
    https://github.com/rogerjdeangelis/utl_dm_command_to_open_last_dataset_in_rwork_library

    see
    https://stackoverflow.com/questions/50494222/dm-command-to-open-last-dataset-in-rwork-library

     1. To view last dataset created
          Push down on the scroll button

     2. To view ANY dataset in the program, log or output screen
          Highlight dataset in (program, log, output or SAS notepad and hit middle mouse button

     If you have real SAS on the your power workstation, and a PERSISTENT'
        puTTY SSH tunnel to the unix kernal running real SAS (no VMs(anywhere)  and no EG)

     1. To list 40 obs from last datasey
         Hold alt key down and push down on scrool button

     2. To view any dataset that exists in unix
          Highlight dataset. Hold down the alt key hit middle mouse button

    for details see

       https://github.com/rogerjdeangelis?utf8=%E2%9C%93&tab=repositories&q=classic&type=&language=


    This only works in the classic editor all subsequent editors do not
    support all the SAS scripting commands.


    Below is example code to run any unix command from your power worstation and
    have the results appear in the log.

    Just type 'xos ls-l' on the command line.

    %macro xos(afstr1)/cmd;

    /* usage xos "ls -l" */

    %syslput afstr1=&afstr1;

    note;notesubmit '%xosa';

    %mend xos;
    %macro xosa;
    rsubmit;
      options nonotes;
      filename xlstcmd pipe &afstr1;
      data _null_;
         file print;
         infile xlstcmd;
         input;
         put _INFILE_;
      run;
      options notes;
    endrsubmit;
    %mend xosa;


