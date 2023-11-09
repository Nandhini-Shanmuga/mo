List of city
Relationship between city & rest
Meal Type

Meal Type +rest + cost +cuisine



#table details

Restaurent

Rest Id | Rest name|cost|city id|Meal Id|cuisine

[ { "_id":323423, 
"rest_id":1,
 "rest_name":"Ama Cafe",
  "city_id":1,
   "cost":450,
   "rating_text":"Very Good", 
   "rating":4.5, 


   "Cuisine":[ 
    { "cuisineid":1, "cuisineName":"North India" }, 
   { "cuisineid":2, "cuisineName":"English Breakfast" },
    { "cuisineid":3, "cuisineName":"Tibetan" } ], 

    "mealTypes":[ 
        { "mealId":1, "mealName":"BreakFast" },
         { "mealId":2, "mealName":"Lunch" }, ] }, 
        
         { "_id":323422, 
         "rest_id":2, 
         "rest_name":"Punjabi Grills",
          "city_id":2,
           "cost":950,
            "rating_text":"Good", "rating":4.1, 

            "Cuisine":[ { "cuisineid":1, "cuisineName":"North India" }, 
            { "cuisineid":4, "cuisineName":"South Indian" } ], 
            
            "mealTypes":[ { "mealId":1, "mealName":"BreakFast", "menu":[ { "type":"Veg", "items":["Panner","Dal"] }, 
            
            { "type":"Non-Veg", "items":["Chicken","Mutton"] } ] }, { "mealId":2, "mealName":"Lunch" }, { "mealId":3, "mealName":"Dinner" } ]

         }
]

collection-2

city[
    {
        _id:1,
        name:"delhi"
    }
    {
        _id:2,
        name:"cbe"
    }
]


function generatedSeries(sequenceName)
{
    var sequenceDocument=db.counters.findAndModify({
        query:{_id:sequneceName}
        update:{$inc:{sequnce_value:1}}
        new:true
    })
    return sequenceDocument.sequence_value
}