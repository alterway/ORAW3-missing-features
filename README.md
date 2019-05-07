
docker build -t oraw3_missing-features
docker run --rm -it --name oraw3 --env BACKEND_SS=http://localhost:8080/issue_weighting --env BACKEND_RI=http://localhost:9704/issue_weighting --net host oraw3_missing-features

GET localhost:8081/tracker?t=un titre original&b=pour une histoire bien vide
returns:
{
    "topScoringIntent": {
        "intent": "Demand"
    }
}