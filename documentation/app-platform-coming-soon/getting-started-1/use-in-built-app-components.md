# Use in-built App components

***

## Hello World - Create Data Table

***

#### 1. To App Platform!

You know that `my_first_page` page we created earlier? Let's go back there and into the page builder... remember, arrow in the action column?

![](https://dubble-prod-01.s3.amazonaws.com/assets/d44d3fb1-fd6e-499f-adad-ec3a92499121.png?0)

#### 2. Component Library

In the component library, we have a BUNCH of pre-built components that you can simply drag and drop onto the App Builder canvas and start using. Feel free to experiment with them if you want!

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/5ff8fb41-ef51-46a2-b6fe-04057b2d0b52/2.5/2.8160589089059/5.2310371565216?0)

#### 3. Click on Data Table

In our Hello World project, we're going to use the Data Table. This component allows us to utilise a workflow to generate the content of the table.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/00765b9e-4cf2-4f5f-aa98-d0c8775b6f2a/2.5/10.335974675259/70.308926090949?0)

#### 4. Add a Data Source

Once the data table has been dragged onto the empty canvas, click on "Add a Data Source"

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/fe54992f-d268-4718-8c4f-ea2f68ee8e51/2.5/66.064794347185/17.080011342854?0)

#### 5. Click on Run Workflow On Load

Choosing "Run Workflow on Load" ensures that whenever the page is loaded, the latest data comes in. "Use Latest Workflow" could be used if you were returning data on a cron and didn't want to load it every time for instance.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/2a4dea09-db5c-47cf-9f1e-b982d08d919c/2.5/19.255788770229/33.328401387621?0)

#### 6. Choose Workflow Output

Once the workflow has finished, you'll see `form_output` in the available list

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/6101d928-2856-4483-a669-08e9ac0446cd/2.5/19.255788770229/49.021511027994?0)

#### 7. Click on Submit

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/51106ede-8b17-4a86-9b90-1a0bc9e10583/2.5/81.947191967188/90.590874257042?0)

#### 8. Click on Hide View column

Now we'll hide some columns that you don't need to display to the user. Next to View and Trigger ID, click the dots and select the Hide X Column.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/a706e094-8e7b-4676-aca4-9abb1d30331a/2.5/72.765285881591/49.511276501204?0)

#### 9. Click on Hide Trigger Id column

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/3b9343ba-92a1-4dbb-bed5-b3769a1ad79d/2.5/87.218387791368/43.755446336741?0)

#### 10. Click on Add a Column

Now let's make sure the user can actually get to the form, rather than just view a list.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/afb45bf1-5d11-4abc-8f84-bf09180133a2/2.5/95.814812408871/45.048936679245?0)

#### 11. Accessor

In the Accessor dropdown, select the `view` key. By leaving the URL blank later on, the action button will automatically use the value from this key. In the Jinja from the last step, we made sure the value was the link to that form.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/454d6415-02d9-4e4b-a24b-f10bca5dd40d/2.2922731242124/50.012881778879/54.584681769507?0)

#### 12. Change the Type

Change the Type to `action`

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/0090aae6-a97f-4852-ad90-894040ec6c25/2.2922731242124/50.012881778879/77.418572277013?0)

#### 13. Change the Column Name

Add a header, which is the column name for this action button.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/60004a87-993c-4eb8-8c8b-8ef38c0ee908/2.2921757115931/50.000996727961/57.1015980728?0)

#### 14. Button Function

Under the Button Function, select the `Open a link` option.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/cf473677-1249-4095-b425-cc2d6186dd55/2.5/32.113830899932/75.584077045205?0)

#### 15. Tooltip

If you want to make your data table more user friendly, you can even add a tooltip to let them know what's going to happen

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/99dcec75-471a-45bd-a6e2-82ac7217d043/2.5/67.908180496581/65.463212270163?0)

#### 16. Test the Page

Hit the Green Play button in the top right, this is a "Test" button that runs the page as if you navigated to it normally. All being well, you should see a list of forms returned with an action column. If you click the link, you should go directly to that form!

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/13730382-b4db-43de-a7f9-9b159a18c9b0/2.5/93.848828559866/1.1339103645518?0)

#### 17. Click on Publish

Publish the page to save it

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/11591c77-f6f5-4a1a-ab02-e7e0b1cf3c4b/2.5/99.666096453609/0.43721714535275?0)

#### 18. Navigate to the page

At the top of the menu bar, you'll see a url that is unique to your app. Clicking this navigates to the page itself, the same one you'll send to your users.

![](https://d3q7ie80jbiqey.cloudfront.net/media/image/zoom/c2fb15ed-2320-42d1-a08a-2c2eb4421de4/2.5/53.71904729945/1.1118548791515?0)

> #### 💡 You're done!
>
> Wow, you've just created your first workflow backed App in Rewst. There was a LOT here, but this is something you can provide to your techs and they can easily navigate to the forms they have access to. It's not the prettiest (yet), but a functional App is an awesome start. Now, let's see what else we can do eh....
