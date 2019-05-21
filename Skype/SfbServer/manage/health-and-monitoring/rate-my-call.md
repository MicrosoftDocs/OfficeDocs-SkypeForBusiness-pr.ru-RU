---
title: Оцените мой звонок в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: Сводка. Узнайте, как оценить возможности моего звонка в Skype для бизнеса Server.
ms.openlocfilehash: e146bba647c9586d96682bf8056417630676726e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279860"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Оцените мой звонок в Skype для бизнеса Server

**Сводка:** Узнайте о том, как оценить возможности моего звонка в Skype для бизнеса Server.

Оцените, что мой звонок был новым компонентом клиентов Skype для бизнеса 2015 и 2016 в Windows, который предоставляет предприятиям способ получить отзыв от своих конечных пользователей.

В окне "скорость звонка" предлагается система оценки звездочки и стандартные маркеры для голосовой связи и видеозвонка. Кроме того, администраторы могут включить настраиваемое поле для обеспечения обратной связи.

Собранные данные оценки вызова в настоящее время не включаются ни в один из существующих ответов мониторинга, но имеет отдельный отчет мониторинга. Данные собираются в таблицы SQL, к которым можно получить доступ с помощью запросов SQL.

## <a name="rate-my-call-prerequisites"></a>Требования функции оценки вызова

Перед тем как пользователи в развертывании сервера Skype для бизнеса Server смогут получить доступ к функциям функций звонков, необходимо развернуть и настроить следующий набор компонентов.

-  На компьютере должен быть установлен Skype для бизнеса Server (версии 9160 или выше).

- Попросите пользователей установить и обновить новейшую версию Skype для бизнеса, а также попросить их использовать пользовательский интерфейс Skype для бизнеса.

- Пользователи должны быть размещены в пуле серверного интерфейса Skype для бизнеса Server.

- Необходимо, чтобы база данных мониторинга сервера Skype для бизнеса Server была развернута и связана с пулами сервера Skype для бизнеса.

- Рекомендуется развернуть панель мониторинга качества вызовов (CQD).

## <a name="configure-rate-my-call"></a>Настройка функции оценки вызова

Функция "оценить мой Звонок" включена по умолчанию в политике клиента со следующими параметрами:

- Оцените процент отображения моего звонка-10%

- Оценить мой звонок разрешить отзыв пользовательских пользователей — отключено

Никаких действий, необходимых для включения базового компонента, не требуется, но если вы хотите включить пользовательскую обратную связь, вам нужно будет включать ее отдельно. Следующий командлет Windows PowerShell — это пример включения настраиваемой обратной связи с конечным пользователем и изменения интервала с 10 до 80%.

```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Доступ к данным оценки вызова

Данные пользователей собираются в двух таблицах в базе данных мониторинга.

 **[Коеметрикс]. [dbo]. [Каллкуалитифидбакктокен]** -в этой таблице содержатся результаты опроса маркеров конечными пользователями.

 **[Коеметрикс]. [dbo]. [Каллкуалитифидбакктокендеф]** -в этой таблице содержатся определения маркеров.

Определения маркеров имеют следующую кодировку:

|||
|:-----|:-----|
|1  <br/> |Искаженная речь  <br/> |
|2  <br/> | Оценка качества <br/> |
|3  <br/> | Фоновый шум <br/> |
|4  <br/> |Приглушенная речь  <br/> |
|5  <br/> |Эхо  <br/> |
|Порт  <br/> | Застывшее видео <br/> |
|максималь  <br/> | Мозаичное видео <br/> |
|стр  <br/> | Размытое изображение <br/> |
|24  <br/> | Блеклые цвета <br/> |
|24  <br/> | Затемненное видео <br/> |
|101  <br/> |Аудио_силентлокал  <br/> |
|102  <br/> |Аудио_силентремоте  <br/> |
|103  <br/> |Аудио_ечо  <br/> |
|104  <br/> |Аудио_баккграундноисе  <br/> |
|105  <br/> |Аудио_ловсаунд  <br/> |
|106  <br/> |Аудио_дроппед  <br/> |
|107  <br/> |Аудио_дистортедспич  <br/> |
|108  <br/> |Аудио_интерруптед  <br/> |
|109  <br/> |Аудио_осер  <br/> |
|201  <br/> |Видео_нолокалвидео  <br/> |
|202  <br/> |Видео_норемотевидео  <br/> |
|203  <br/> |Видео_ловкуалити  <br/> |
|204  <br/> |Видео_фрозенвидео  <br/> |
|205  <br/> |Видео_стоппедунекспектедли  <br/> |
|206  <br/> |Видео_дарквидео  <br/> |
|207  <br/> |Видео_ноаудиосинк  <br/> |
|208  <br/> |Видео_осер  <br/> |
|301  <br/> |Пстн_диалпад  <br/> |
|401  <br/> |Сс_ноконтентлокал  <br/> |
|402  <br/> |Сс_ноконтентремоте  <br/> |
|403  <br/> |Сс_кантпресент  <br/> |
|404  <br/> |Сс_ловкуалити  <br/> |
|405  <br/> |Сс_фризинг  <br/> |
|406  <br/> |Сс_стоппедунекспектедли  <br/> |
|407  <br/> |Сс_ларжеделай  <br/> |
|408  <br/> |Сс_осер  <br/> |
|501  <br/> |Релиабилти_жоин  <br/> |
|502  <br/> |Релиабилти_инвите  <br/> |

 **[Коеметрикс]. [dbo]. [Каллкуалитифидбакк]** В этой таблице содержатся результаты опроса от "звезды" голосования и отзывов пользователей, если они включены.

Данные из таблиц можно вызвать с помощью запроса **SELECT \* from [Table.name]** или с помощью Microsoft SQL Server Management Studio.

Можно использовать следующие запросы SQL:

 **Аудио**

```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **Видео**

```
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>Обновление определений маркеров

Последние клиенты Skype для бизнеса сообщают о новых кодах маркеров проблем\> (100), которые могут отсутствовать в [коеметрикс]. [dbo]. Таблица [Каллкуалитифидбакктокендеф]. Чтобы обновить таблицу базы данных с помощью последних определений маркеров, в базе данных мониторинга с помощью Microsoft SQL Server Management Studio можно выполнить указанную ниже команду SQL. Эта команда заменит все записи в элементе [Коеметрикс]. [dbo]. Таблица [Каллкуалитифидбакктокендеф].

```
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


