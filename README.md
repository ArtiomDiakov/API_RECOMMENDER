# ML_OPS MVP RECOMMENDER USER-ITEM ON STEAM USERS

A FastAPI application that provides game recommendations and user data analysis on some example requests.

## Endpoints

- `POST /recommend`: Recommend games to a user. User must have >= 200 games in library.
- `GET /developer`: Get developer stats the response show year, games per this particular year, and free games for that year
- `GET /userdata`: Get user data. Althougt not working on render VPS free tier properly, mostly because a huge dataset,
but with enough memory shows per particular user, money spend on games, recommended games percentage, and quantity of items.

## Requirements

- Python 3.8+
- See `requirements.txt` for dependencies.

## Setup Locally

1. Clone the repository
2. Install requirements
3. Navigate to your project folder and run uvicorn app.main:app --host 0.0.0.0 --port 8000
4. Open your browser and navigate to http://127.0.0.1:8000/docs to try endpoints

## Tests
- `POST /recommend`
{
  "user_id": "-Mad-"
}
Response:
{
  "user_id": "-Mad-",
  "recommended_games": [
    "Call of Duty®: Black Ops II",
    "ARK: Survival Evolved",
    "Arma 3",
    "Chivalry: Medieval Warfare",
    "XCOM: Enemy Unknown"
  ]

  
- `GET /developer`
Konami
Response:
{
  "developer": "Konami",
  "stats": [
    {
      "year": 2017,
      "cantidad_items": 3,
      "contenido_free": 66.67
    },
    {
      "year": 2016,
      "cantidad_items": 6,
      "contenido_free": 0
    },
    {
      "year": 2015,
      "cantidad_items": 8,
      "contenido_free": 0
    }
  ]
}

- `GET /userdata`
-Mad-
Response:
{
  "usuario": "-Mad-",
  "dinero_gastado": "1680.62 USD",
  "porcentaje_recomendacion": "100.00%",
  "cantidad_items": 367
}
