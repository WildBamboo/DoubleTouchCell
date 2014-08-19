UITableView appears to have a bug when the 'bounces' property is NO
where by certain cells will not respond on the first touch. These
cells will respond on the second and subsequent touches.

To see this in action, run this example via Xcode so you can also
see the logs. There are at least two ways to reproduce this issue,
and possibly more. 

1. Load the app.
2. Touch the first cell labelled 0, observe the touch registering.
3. Swipe the table view down, in an attempt to scroll the table view
up. This will do nothing of course, because you are already at the top,
but this step needs to be performed.
4. Touch the first cell again. Observe the touch not registering.
5. Touch the first cell a second time. Observe the touch now registering.

Similarly, this issue can be seen with the last cell labelled 4.

1. Scroll all the way to the bottom.
2. Swipe the table view up again, in at attempt to scroll past the
bottom. This will do nothing of course, because you are already at
the bottom.
3. Touch the last cell. Observer the touch not registering.
4. Touch the last cell a second time. Observe the touch now registering.


If you enable the 'bounces' property, I cannot reproduce this issue.
