---
title: Устранение неполадок потоковой трансляции в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: В этой статье рассматриваются варианты устранения неполадок для событий потоковой передачи Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767996"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Устранение неполадок трансляций в Microsoft Teams

> [!IMPORTANT]
> **Китай**. Пользователи, расположенные в Китае, не смогут настраивать и посещать трансляции Teams или Yammer или просматривать видео по запросу, так как в настоящее время сеть Azure CDN, на которую полагаются эти приложения, может быть недоступна в Китае.
>
> Администратору может потребоваться настроить VPN для подключения корпоративной сети, чтобы эти приложения работали без проблем. После этого люди из вашей организации смогут планировать трансляции и посещать их.

## <a name="before-a-live-event"></a>Перед трансляцией

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>Убедитесь, что все события доступны в сети

#### <a name="general-teams-endpoints"></a>Общие конечные точки Teams

Для Teams требуется подключение к Интернету. Все конечные точки, перечисленные [в Office 365 конечных точках для Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2), должны быть доступны пользователям Teams в сети вашей организации.

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Динамические события Кодировщика Teams — конечные точки приема RMTP

Чтобы получить видеопоток для трансляции кодировщика Teams, отправляемой в Teams из кодировщика, вам потребуется доменное имя и порты, открытые в брандмауэре сети:

- Домены: *.rtmpingest.mcr.teams.microsoft.com
- Порты: 1935/1936 (для RTMP/RTMPS)

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>Убедитесь, что у вас достаточно пропускной способности отправки

При создании или потоковой передаче трансляции через RTMP может быть недостаточно пропускной способности передачи через Интернет на сайте, отправляя прямой трансляции. Низкая пропускная способность отправки может привести к снижению кадров или проблемам в самом видеотрансляций, что может привести к проблемам с воспроизведением для зрителей.

Убедитесь, что скорость передачи для компьютера и сети, отправляющей трансляцию, выше скорости, заданной для динамического потока. Если вы выводите поток со скоростью 5 Мбит/с из кодировщика, но скорость передачи близка к или ниже этой скорости, могут возникнуть проблемы с недостаточной скоростью передачи потока.

Если у вас возникли проблемы с пропускной способностью передачи, попробуйте выполнить следующие действия.

1. Используйте жесткое подключение Ethernet для любой машины, с помощью которых вы толкаете поток, чтобы избежать спадов в Wi-Fi.
1. Уменьшите скорость кодирования вашего динамического канала до значения, значительно ниже максимальной скорости передачи.

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>Подготовка сети для множества одновременных просмотров

Во время трансляций многие люди присоединятся, чтобы посмотреть ваше событие в прямом эфире. Это может привести к нагрузке на вашу сеть и пропускную способность загрузки Через Интернет. Необходимо оценить текущую сетевую инфраструктуру и убедиться, что пользователи в корпоративной сети будут иметь пропускную способность, необходимую для просмотра трансляции. Чтобы уменьшить интернет-трафик, необходимый для трансляций, существует два варианта:

1. Настройте существующие прокси-серверы кэша в сети для кэширования видео из Teams.
1. Используйте стороннее решение для доставки видео eCDN для оптимизации видеопотока.

### <a name="i-cant-create-a-live-event"></a>Не удается создать трансляцию

В Microsoft Teams и Yammer есть разрешения, необходимые пользователю для создания трансляции в зависимости от того, какую службу вы используете для трансляции.

1. Убедитесь, что администратор Teams включил вас для создания трансляций.
1. Обратитесь к администратору, что у вас есть действительная лицензия Teams, которая позволяет создавать трансляции.

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>Убедитесь, что у зрителей есть разрешение на просмотр события

Трансляции Microsoft Teams имеют несколько разных ролей для разрешений на само событие (организатор, продюсер, выступающий, участник).

Дополнительные сведения см. в разделе [Роли групп событий Microsoft Teams](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) .

## <a name="producing-a-live-event"></a>Создание трансляции

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>Я не знаю, как настроить кодировщик

Самый простой способ приступить к работе — следовать инструкциям, приведенным в статье [Использование кодировщика для потоковой трансляции в Microsoft Teams](teams-encoder-setup.md) .

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>Кодировщик не подключается к URL-адресу приема сервера

- Убедитесь, что URL-адрес RTMP правильно введен в качестве выходных данных кодировщика.
- Убедитесь, что ключ RTMP правильно введен в качестве выходных данных кодировщика.
- Проверьте состояние подключения к Интернету, чтобы убедиться, что кодировщик подключен и подключен к сети.
- Возможно, у вас есть параметры безопасности сети или брандмауэра, которые могут блокировать выходные данные подключения.
- Кодировщик может не поддерживаться в Teams. Ознакомьтесь со списком протестированных кодировщиков в статье [Использование кодировщика для потоковой трансляции в Microsoft Teams](teams-encoder-setup.md).

### <a name="i-cant-get-rtmps-to-work"></a>Я не могу заставить RTMP работать

- Некоторые кодировщики могут поддерживать другую реализацию, которая не поддерживается Teams. Ознакомьтесь со списком протестированных кодировщиков, которые работают с Teams в [статье Использование кодировщика для потоковой трансляции в Microsoft Teams](teams-encoder-setup.md).
- Не все кодировщики или версии поддерживают RTMP. Обратитесь к производителю или создателю программного обеспечения, чтобы узнать, что они поддерживают.

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>Я пытался запустить настройку, и это занимает много времени

Как правило, настройка может занять несколько минут, прежде чем вы сможете начать отправку кодировщика. Если служба занята, это может занять больше времени, поэтому рекомендуется дать достаточно времени, чтобы начать настройку перед запланированным трансляцией.

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>Я пытался запустить настройку, но происходит слишком много событий

Если при запуске события появляется сообщение о том, что достигнуто максимальное количество событий, обратитесь к администратору Teams, который может остановить другие события, чтобы освободить место для события с более высоким приоритетом.

### <a name="i-cant-see-producer-view"></a>Представление производителя не отображается

1. После начала потоковой передачи из кодировщика может потребоваться несколько секунд.
1. Убедитесь, что кодировщик подключен к Teams.
1. Иногда это может помочь обновить страницу в Teams. Вам может быть предложено покинуть страницу; Это не повлияет на трансляцию.
1. Некоторые сети могут блокировать доступ к содержимому. Убедитесь, что параметры сетевой безопасности и брандмауэра разрешают использование протокола RTMP, а [необходимые домены](/microsoft-365/enterprise/urls-and-ip-address-ranges) находятся в списке разрешенных. Это поможет проверить, работает ли она в другой сетевой среде, независимо от корпоративной сети, VPN или заблокированной сети.

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>Мой канал выглядит плохо, имеет плохое качество, или глиш

1. Проверьте пропускную способность передачи с компьютера, с который вы отправляете трансляцию. Низкая пропускная способность может привести к снижению кадров, плохому качеству или сбою видеопотока. Вам требуется пропускная способность передачи, которая превышает скорость передачи.
1. Убедитесь, что вы используете рекомендуемые параметры кодировщика для Teams. Дополнительные сведения см [. в статье Ручная настройка кодировщиков для потоковой трансляции событий в Microsoft Teams](teams-encoder-configuration.md) .
1. Убедитесь, что аудио- и видео, поступающие в кодировщик, не имеют никаких проблем. Исходные аудио- или видеопотоки, перенаправленные в кодировщик, могут иметь сами проблемы, что приведет к плохому взаимодействию, отправленном зрителям.
1. Проверьте загрузку ЦП в кодировщике. Возможно, вы максимально используете ЦП с исходным содержимым и (или) с скоростью передачи. Если загрузка ЦП слишком высока, попробуйте уменьшить сложность наложения или содержимое веб-канала или уменьшить скорость потоковой передачи.
1. Убедитесь, что кодировщик обновлен. Если это аппаратный кодировщик, убедитесь, что у вас есть последние обновления встроенного ПО. Если это программный кодировщик, убедитесь, что используется последняя версия.
1. Попробуйте сбросить или перезапустить кодировщик. Обратите внимание, что если это сделать во время трансляции, во время воспроизведения во время перезапуска кодировщика зрители увидят ошибку. После перезапуска потоковой трансляции из кодировщика зрителям потребуется перезагрузить страницу, чтобы снова получить трансляцию.

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>Я закончил трансляцию из моего кодировщика, но зрители видят ошибку

Выберите **Остановить событие** перед отключением кодировщика. Если вы уже отключили кодировщик, вы по-прежнему можете выбрать **Остановить событие**, но зрители могут увидеть ошибку.

### <a name="my-viewers-are-seeing-issues"></a>Мои зрители видят проблемы

- Если одно средство просмотра сообщает о проблеме, убедитесь, что средство просмотра имеет достаточную пропускную способность и имеет хорошее подключение к Интернету, чтобы наблюдать за событием.
- Если у нескольких пользователей в одной сети возникают проблемы, возможно, возникают проблемы, связанные с перегрузкой сети. Ознакомьтесь [с разделом Масштабирование доставки видео и мониторинг сетевого трафика с помощью eCDN в Microsoft Teams](teams-stream-ecdn.md) , чтобы узнать, можно ли определить решение проблемы.
- Часто, когда несколько зрителей видят проблему, она фактически связана с каналом кодировщика.
  - Убедитесь, что кодировщик правильно задан в соответствии со спецификациями, описанными в настройке кодировщика, и правильно настроен.
  - Убедитесь, что для потоковой передачи достаточно пропускной способности. Вы можете попытаться уменьшить пропускную способность выходных данных кодировщика.
  - Иногда сброс кодировщика помогает, но обратите внимание, что при повторном подключении необходимо сохранять те же параметры. Участники аудитории могут увидеть ошибку или сбой в трансляции.

### <a name="i-or-my-viewers-cant-hear-the-video"></a>Я или мои зрители не слышат видео

1. Убедитесь, что кодировщик отправляет звук.
1. Убедитесь, что аудиоустройство подключено.
1. Если используется Windows, убедитесь, что выбрано правильное звуковое устройство.
1. Если произошел сбой кодировщика, некоторые браузеры или устройства не смогут восстановить и воспроизвести звук правильно.

> [!NOTE]
> Если вы развернули eCDN Майкрософт в качестве поставщика видеораздачи для трансляций, дополнительные сведения об устранении проблем с [производительностью eCDN см. в статье Устранение проблем с производительностью eCDN](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) .