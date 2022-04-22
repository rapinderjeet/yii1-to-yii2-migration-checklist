Variable Replacement:
-> Yii::app()->input -> Yii::$app->request
-> $session->add() -> $session->set()
-> Yii::app() -> Yii::$app

Namespaces:
-> All files must be used to use namespace in YII2.

Database:
-> addCondition function in YII1 should be replaced with where function in YII2.
-> Model relations must be updated since they use new format now.
-> Find by PK must be replaced when quering the database 
  eg: SViews::model()->findByPK($id); -> SViews::findOne($id);
-> Primary key is different in yii1 and yii2.
	YII1:
	public function primaryKey() 
	{
		return 'name';
	}
	YII2:
	public $primaryKey = 'ListingID';
-> Specifing the table need to be static method instead of non static in Yii1.

Helpers:
-> CJSON::encode -> yii\helpers\Json::encode()
-> Html::dropDownList is using different syntax. You need to add 'id' options manually.

Deployment:
-> Yii1 loads under root but Yii2 loaded in web.

Caching:
-> All caching logics need to be rewritten.

Email:
-> YiiMailMessage must be replace with new mail classes

Extensions:
-> ext.EPhpThumb.EPhpThumb  has be replaced with Image::thumbnail($newFilePath, 160, 160)->save('path_to_new_file', ['quality' => 80]);
