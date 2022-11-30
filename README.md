# How to display a particular day and time in day view of Xamarin.Forms Schedule (SfSchedule)

You can configure the day view as per your requirements in Xamarin.Forms [SfSchedule](https://www.syncfusion.com/xamarin-ui-controls/xamarin-scheduler).

**XAML**

You can disable the navigation by setting the [EnableNavigation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_EnableNavigation) property of the schedule and avoid the vertical scrolling by setting the [StartHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.DayViewSettings.html#Syncfusion_SfSchedule_XForms_DayViewSettings_EndHour) properties of [DayViewSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_DayViewSettings).  By setting [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.SfSchedule.html#Syncfusion_SfSchedule_XForms_SfSchedule_TimeIntervalHeight) to -1, you can view the scheduler in full screen.

```
<schedule:SfSchedule x:Name="Schedule"
                    DataSource="{Binding Meetings}"
                    ScheduleView="DayView"
                    EnableNavigation="False"
                    TimeIntervalHeight="-1"
                    Margin="0">
    <schedule:SfSchedule.DayViewSettings>
        <schedule:DayViewSettings StartHour="11" EndHour="20"/>
    </schedule:SfSchedule.DayViewSettings>
    <schedule:SfSchedule.AppointmentMapping>
        <schedule:ScheduleAppointmentMapping
                        ColorMapping="Color"
                        EndTimeMapping="To"
                        StartTimeMapping="From"
                        SubjectMapping="EventName"
                        />
    </schedule:SfSchedule.AppointmentMapping>
 
    <schedule:SfSchedule.BindingContext>
        <local:SchedulerViewModel/>
    </schedule:SfSchedule.BindingContext>
</schedule:SfSchedule>
```
**C#**

By setting MoveToDate in the schedule, you can move to the specific date in schedule.
```
  this.schedule.MoveToDate = DateTime.Now.Date.AddHours(11);
```

KB article - [How to display a particular day and time in day view of Xamarin.Forms Schedule (SfSchedule)](https://www.syncfusion.com/kb/12274/how-to-display-a-particular-day-and-time-in-day-view-of-xamarin-forms-schedule-sfschedule)