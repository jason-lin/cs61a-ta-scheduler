# CS 61A TA Scheduler #

### Acknowledgements ###
Almost all of this code came from Marvin Zhang's TMC Scheduler (https://github.com/zhangmarvin/scheduler), which was based off the original CS 61A TA scheduler by Robert Huang (https://github.com/robhuang/assign-sections).

### Setup ###
Note: The author has only seen success with setup on Mac. Set up on Windows at your own risk.
- Make sure Python 2.7 is installed on your computer. Any recent version should do.
- Install the lpsolve library for Python according to these instructions: http://racingtadpole.com/blog/install-lpsolve-for-python/

### Usage ###

Run the scheduler with the command:

    python ta_scheduler.py -s in.csv out.csv

The `in.csv` file should be in the format:

    |Name| |Number of sections to be assigned to| |Section 1 preference| |Section 2 preference| ... |Section n preference|

where section 1 is the most desired and section `n` is the least desired. The section number should correspond to the keys in the `SECTION_TO_TIMES` dictionary at the top of the `ta_scheduler.py` file. So for example, if a TA wants T/Th 12:30-2PM, you'd put down 2 in the CSV file column.

The `out.csv` file has the following format:

    |Name| |Time of assigned section 1| ... |Time of assigned section n| |Section number of assigned section 1| ... |Section number of assigned section n|

Indicate any parallel sections in the `SECTION_TO_SECTION_NUMS` dictionary (ex. In the `example_in.csv` file, sections 11, 12, 34, and 39 all happen during slot 0, Tu/Th 9:30 AM to 11 AM).

`SECTION_CAPS` can be used to schedule more than one TA per section during a given timeslot. Otherwise, the cap value should be the number of sections happening during that section slot.

You can run the provided example with the following command:

    python ta_scheduler.py -s sample_in.csv sample_out.csv
