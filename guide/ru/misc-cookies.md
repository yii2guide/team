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

## Объявить composer-пакеты

Иногда нужно по-быстрому сгенерить пакет и сразу начать с ним работать без обновления всех зависимостей.

В `env-local` объявите пакеты так:

```php
use yii2lab\extension\package\helpers\PackageHelper;

return [
	// ...
	'aliases' => PackageHelper::generateAliases([
		'yii2game/engine',
		'yii2game/evo',
	]),
	// ...
];
```
	
Либо выполнить команду:

```php
use yii2lab\extension\package\helpers\PackageHelper;

PackageHelper::forge('yii2game', 'engine');
```

 * проверка на существование репозитория
 * клон (если нет)
 * прописывается алиас для автозагрузки
 * добавляется в composer.json