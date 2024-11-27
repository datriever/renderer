# Energy Consumption Report

## Consumption Distribution

Most of the energy consumption last year came from the grid. The newly installed solar panels had a significant contribution.

```plot
{
  "data": [
    {
      "type": "pie",
      "labels": ["Grid", "Natural Gas", "Solar"],
      "values": [8423380, 1684676, 1293527],
      "textinfo": "label+percent",
      "hoverinfo": "label+value+percent",
      "hovertemplate": "%{label}: %{value:.0f}kWh (%{percent})",
      "rotation": 90
    }
  ],
  "layout": {
    "title": "Consumption Distribution (kWh)"
  }
}
```

## Cost Distribution

Due to the high prices, the grid dominated the price.

- Total expenditure was close to 630,000€. 
- Solar panels reduced costs by 10%, saving over 70,000€

```plot
{
  "data": [
    {
      "type": "pie",
      "labels": ["Grid", "Natural Gas", "Solar"],
      "values": [574322, 57664, 70331],
      "textinfo": "label+percent", "hovertemplate": "%{label}: %{value:.0f}€ (%{percent})",
      "rotation": 90
    }
  ],
  "layout": {
    "title": "Cost Distribution (€)"
  }
}
```