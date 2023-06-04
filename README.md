- 👋 Hi, I’m @maija0105
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
maija0105/maija0105 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->if '__PHP2PY_LOADED__' not in globals():
    import os, os.path, sys
    __compat_layer = os.getenv('PHP2PY_COMPAT', 'php_compat.py')
    if not os.path.exists(__compat_layer):
        sys.exit(f'[-] Compatibility layer not found in file {__compat_layer}. Aborting.')
    # end if
    with open(__compat_layer) as f:
        exec(compile(f.read(), '<string>', 'exec'))
    # end with
    globals()['__PHP2PY_LOADED__'] = True
# end if
import inspect
php_print("""// <Snippet3>
MLContext mlContext = new MLContext(seed: 0);
// </Snippet3>
// <Snippet5>
var model = Train(mlContext, _trainDataPath);
// </Snippet5>
// <Snippet14> Evaluate(mlContext, model);
// </Snippet14>
// <Snippet20> TestSinglePrediction(mlContext, model);
// </Snippet20>
}
public  static  ITransformer    Train(MLContext mlContext,  string dataPath)
{
// <Snippet6>
IDataView   dataView    =   mlContext.Data.LoadFromTextFile<
>(dataPath, hasHeader: true, separatorChar: ',');
// </Snippet6>
// <Snippet7>

var pipeline    = mlContext.Transforms.CopyColumns(outputColumnName inputColumnName:
// </Snippet
// <Snippet10>
.Append(mlContext.Regression.Trainers.FastTree());
// </Snippet10>
Console.WriteLine("=============== Create  and Train   the Model ===============");
// <Snippet11>
var model = pipeline.Fit(dataView);
// </Snippet11>
Console.WriteLine("=============== End of  training
===============");
Console.WriteLine();
// <Snippet12> return model;
// </Snippet12>
}

model)

private static void Evaluate(MLContext mlContext, ITransformer
{
// <Snippet15>
IDataView   dataView    =   mlContext.Data.LoadFromTextFile<

>(_testDataPath, hasHeader: true, separatorChar: ',');
// </Snippet15>
// <Snippet16>
var predictions = model.Transform(dataView);
// </Snippet16>
// <Snippet17>

var metrics =   mlContext.Regression.Evaluate(predictions, "Label", "Score");
// </Snippet17>
}
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{
//Prediction test
// Create prediction function and make prediction.
// <Snippet22>
var predictionFunction  = mlContext.Model.CreatePredictionEngine<TaxiTrip, TaxiTripFarePrediction>(model);
// </Snippet22>
//Sample:
//vendor_id,rate_code,passenger_count,trip_time_in_secs,trip_distance, payment_type,fare_amount
//VTS,1,1,1140,3.75,CRD,15.5
// <Snippet23>
};
// </Snippet23>
// <Snippet24>
= predictionFunction.Predict(taxiTripSample);
// </Snippet24>
  
