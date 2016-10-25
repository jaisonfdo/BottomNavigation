# BottomNavigation
A sample app for Bottom Navigation View with ViewPager 
![ScreenShot](http://droidmentor.com/wp-content/uploads/2016/10/BNV_with_ViewPager.jpg)

For connecting BottomNavigationView with ViewPager, you need to follow thesesteps

1. First, you need to create an application with latest Design Support Library(25) to your build.gradle to use BottomNavigationView.

2. Then add all the necessary resources ( color, drawable’s ) to the resource directory.

3. Create a view with ViewPager and BottomNavigationView

4. Create necessary fragments for each tab on the viewpager.
 
5. Then setup the viewpager using fragments and viewpager adapter.

6. Add OnNavigationItemSelectedListener for BottomNavigationView, and override OnNavigationItemSelected method with the relevant action.

7. Once done with the previous step add OnPageChangeListener to the ViewPager and override the PageSelected method. The magic happens here, the following code selects the relevant item in the BottomNavigationView.

<pre>
@Override
    public void onPageSelected(int position) {
        if (prevMenuItem != null) {
            prevMenuItem.setChecked(false);
        }
        else
        {
            bottomNavigationView.getMenu().getItem(0).setChecked(false);
        }
       
        bottomNavigationView.getMenu().getItem(position).setChecked(true);
        prevMenuItem = bottomNavigationView.getMenu().getItem(position);
    }
 </pre>


For more information, check out my detailed guide here : http://droidmentor.com/bottomnavigationview-with-viewpager-android
