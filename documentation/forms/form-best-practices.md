# Form Best Practices

There are often multiple ways to achieve a single goal, however, there are certain best practices that should be followed when interacting with Rewst to ensure that you get the best performance with your forms.

### Conditional Fields&#x20;

You will often have forms that you want to use across a multitude of clients, but sometimes fields may not be relevant to them all. Rewst has "Conditional Fields" that can be used to determine whether you show another field.

In our example, we will look at the Supervisor field when creating a new user. In the image below, we have no Supervisor set and therefore the following field is another dropdown for further information.

<figure><img src="../../.gitbook/assets/no-supervisor-example (1).png" alt=""><figcaption></figcaption></figure>

You can then see if we add content to that supervisor dropdown, which is a list of users pulled dynamically from M365, that a new field appears.

<figure><img src="../../.gitbook/assets/supervisor-set1.png" alt=""><figcaption></figcaption></figure>

This boolean field is then ticked, which gives access to another relevant field.

<figure><img src="../../.gitbook/assets/supervisor-set2.png" alt=""><figcaption></figcaption></figure>

The idea here is that rather than giving fields to a user that bear no relevance, you only give them fields they must fill in.

These conditional fields are set by clicking the field on the form and pressing the "Set Conditional Field" button, which presents you with the below.

<figure><img src="../../.gitbook/assets/field-conditions.png" alt=""><figcaption></figcaption></figure>
