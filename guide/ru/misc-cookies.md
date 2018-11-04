Рецепты
===

## Версия PHP

	PHP_VERSION

## Версия Yii

	Yii::getVersion()

## Версия приложения

	Yii::$app->version

## Список композер-пакетов

	Yii::$app->extensions

## Динамические вкладки

```php
\yii\bootstrap\Tabs::widget([
	-
	'items' => [
		[
			'label' => Yii::t('profile/security', 'password'),
			'content' => $this->context->renderPartial('password', ['model' => $modelPassword]),
		],
		[
			'label' => Yii::t('profile/security', 'email'),
			'content' => $this->context->renderPartial('email', ['model' => $modelEmail]),
		],
	],
]) ?>
```

## Автообновление пакетов

Хук git: Если после git pull есть изменения в composer.json, то делать composer update
