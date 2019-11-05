# Lesson 12 - Instances

# Exercise: Treehouse Pulley

In this exercise, you're using code to decide whether it's safe to add items to a basket that will be delivered to your treehouse by a pulley.

## Exercise
Create three constants for items of different weights that you'd like to bring up to your fort: one less than 100, one between 100 and 1000, and one over 1000.

```swift
let lightWeightArmchair = 90 // less than 100
let middleWeightBear = 500 // between 100 and 1000
let heavyWeightBlueWhale = 1100 // over 1000
```

## Exercise
A lightweight treehouse pulley is already created below. But you've decided that you want to be able to lift, say, a small horse or piano up to your fort, so you’re installing a second pulley with a much bigger basket.
Create a second pulley that has a higher capacity and can hold at least ten times the weight of the ricketyRope.

```swift
var ricketyRope = TreehousePulley(weightCapacity: 200)
var secondPulley = TreehousePulley(weightCapacity: ricketyRope.weightCapacity * 10) // a second pulley 10 times the weight of ricketyRope. Needs to be a `var` since you're going to add items into the big basket.
```

## Exercise
Use the TreehousePulley type's addLoadToBasket method to add the items you defined above. Add three of the lightest item, two of the middle-weight item, and one of the heaviest item. Add the items to the lightweight pulley first, using the canHandleAdditionalLoad method to check whether the item would overload the pulley, then move on to your stronger pulley when the first is fully loaded.
If your pulleys together aren't enough to hold all the items you need, create a third super heavy-duty pulley to finish the job.
 
```swift
//Solution Without Loops

var ginormousBasket = TreehousePulley(weightCapacity: 100000000) // created a third, super heavy-duty pulley

// Add the first light-weight item to the ricketyRope if it can hold the weight. If it can, add it. If it can't, check to see if the secondPulley can handle a light-weight item. If it can, add it. If it can't, add it to the ginormousBasket.

if ricketyRope.canHandleAdditionalLoad(lightWeightArmchair) {
    ricketyRope.addLoadToBasket(loadWeight: lightWeightArmchair)
} else if secondPulley.canHandleAdditionalLoad(lightWeightArmchair) {
    secondPulley.addLoadToBasket(loadWeight: lightWeightArmchair)
} else {
    ginormousBasket.addLoadToBasket(loadWeight: lightWeightArmchair)
}

// Add the second light-weight item to the right basket.

if ricketyRope.canHandleAdditionalLoad(lightWeightArmchair) {
    ricketyRope.addLoadToBasket(loadWeight: lightWeightArmchair)
} else if secondPulley.canHandleAdditionalLoad(lightWeightArmchair) {
    secondPulley.addLoadToBasket(loadWeight: lightWeightArmchair)
} else {
    ginormousBasket.addLoadToBasket(loadWeight: lightWeightArmchair)
}

// Add the third light-weight item to the right basket.

if ricketyRope.canHandleAdditionalLoad(lightWeightArmchair) {
    ricketyRope.addLoadToBasket(loadWeight: lightWeightArmchair)
} else if secondPulley.canHandleAdditionalLoad(lightWeightArmchair) {
    secondPulley.addLoadToBasket(loadWeight: lightWeightArmchair)
} else {
    ginormousBasket.addLoadToBasket(loadWeight: lightWeightArmchair)
}

// Add the first middle-weight item to the right basket.

if ricketyRope.canHandleAdditionalLoad(middleWeightBear) {
    ricketyRope.addLoadToBasket(loadWeight: middleWeightBear)
} else if secondPulley.canHandleAdditionalLoad(middleWeightBear) {
    secondPulley.addLoadToBasket(loadWeight: middleWeightBear)
} else {
    ginormousBasket.addLoadToBasket(loadWeight: middleWeightBear)
}

// Add the second middle-weight item to the right basket.

if ricketyRope.canHandleAdditionalLoad(middleWeightBear) {
    ricketyRope.addLoadToBasket(loadWeight: middleWeightBear)
} else if secondPulley.canHandleAdditionalLoad(middleWeightBear) {
    secondPulley.addLoadToBasket(loadWeight: middleWeightBear)
} else {
    ginormousBasket.addLoadToBasket(loadWeight: middleWeightBear)
}

// Add the first (and only) heavy-weight item to the right basket.

if ricketyRope.canHandleAdditionalLoad(heavyWeightBlueWhale) {
    ricketyRope.addLoadToBasket(loadWeight: heavyWeightBlueWhale)
} else if secondPulley.canHandleAdditionalLoad(heavyWeightBlueWhale) {
    secondPulley.addLoadToBasket(loadWeight: heavyWeightBlueWhale)
} else {
    ginormousBasket.addLoadToBasket(loadWeight: heavyWeightBlueWhale)
}
```

# Exercise: Identity

What does it really mean for an instance value to have its own identity?

## Exercise
Create a variable for myPlans, initialized to a string describing your evening plans.
Create a second variable for friendPlans, but initialize it to myPlans. (Your friend takes less initiative than you at planning.)
Below the declaration of friendPlans, update myPlans by using the addition operator + to add one more activity.
Check the values of myPlans and friendPlans. Are they the same or different?

```swift
// Create your variables here:
var myPlans = "do assignments, play with Scooter, sleep"


// Update `myPlans` here:
var friendPlans = myPlans
myPlans += ", watch tv in bed!"
```

## Exercise
Create a function addDance that takes a string, appends a phrase about dancing (like "and then we dance!" or "but no dancing", according to your taste), and returns the new string.
Call the addDance function passing in myPlans, and assign the result to friendPlans.

```swift
// Define and call your function here:
func addDance(phrase: String) -> String {
    return "\(phrase), and then we dance!"
}

friendPlans = addDance(phrase: myPlans)
```

## Exercise
How do you expect friendPlans to change? How do you expect myPlans to change?
Print both instances to to find out.

```swift
print("myPlans and friendPlans started out the same, then myPlans added the part about programming. Then friendPlans became equal to myPlans, but with dancing.")

print(friendPlans)
// Output: do assignments, play with Scooter, sleep, watch tv in bed!, and then we dance!

print(myPlans)
//Output: do assignments, play with Scooter, sleep, watch tv in bed!
```
 
