---
title: Политики хранения группами Майкрософт вопросы и ответы
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Часто задаваемые вопросы о политиках хранения в группах Майкрософт.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c8ebd3d35c471a529899cd46a364511f7ea267c
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004580"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Политики хранения группами Майкрософт вопросы и ответы

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Какие типы политики можно настроить в политики хранения и как они работают?

В центр соответствия требованиям и безопасности при настройке политику хранения для группы или любой другой рабочей нагрузки, можно выполнить настройку два основных типа политик: 
- Сохранение: Эти политики убедитесь, что данных сохраняется для заданного периода времени, независимо от того, что происходит в средствах конечного пользователя. Они убедитесь, что данные сохраняются в целях соответствия требованиям, и доступные возможности обнаружения электронных данных до этого времени истечения срока действия. По истечении времени вашей политике можно указать, следует ли ничего не делать, или удалить данные. В группах при создании политики хранения для 7 лет даже в том случае, если конечный пользователь удаляет сообщения, помещенные групп, эти сообщения по-прежнему сохраняются для обнаружения электронных данных для 7 лет.
- Удаления: Эти политики убедитесь, что данные не ответственности для вашей организации. После указанного срока данных удаляется из всех соответствующих хранилища в группах. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Мы включают группами в масштабе организации политики 

Нет, не в настоящее время. Необходимо создать отдельные политики для группы чата и канала сообщений, с помощью строки расположение группы или эти командлеты групп: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Эти командлеты get и задать также версий.

### <a name="are-these-retention-policies-retroactive"></a>Существуют следующие политики хранения имеет обратной силы? 

Да, эти атрибуты. При создании политики хранения для удаления данных возрастом более 60 дней, он удалит групп данных, созданных более 60 дней назад. 

### <a name="what-is-the-default-retention-policy"></a>Что такое политика хранения по умолчанию? 

По умолчанию группы чата, канала и файлы данных, сохраняются навсегда. Можно удалять что-то, но в случае отсутствия политики хранения данных групп всегда архивируются в почтовых ящиков Exchange online (пользователей и групп) и остается обнаружения электронных данных. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Можно распределять наборы пользователей или групп в политике 

Да, это сделать. В мастере создания политики на шаге расположения можно включения или исключения (**сообщения канала команд**) группы или пользователи (**группы чата**) и создание политики для вашей организации. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Что такое основное различие между с помощью строки расположение группы почтовых ящиков и групп канала сообщения расположение строки в политики хранения 

Если вы используете строк расположение почтового ящика пользователя и почтового ящика группы для Exchange Online, групп данные будут удалены из определенных почтовых ящиков. Тем не менее удаляются данные из почтового ящика. Он не удаляет данных других групп, таких как службы бесед. Мы рекомендуем использовать политики хранения групп для правильного управления все данные команды. Политики хранения группы удаляет данные, группы из всех службы чата расположений — почтовые ящики, хранения, группам клиентов. 

Примечание: Запуск компонента политик хранения для групп следит за тем, что только политики групп удаление групп элементов, хранятся в расположениях почтовых ящиков Exchange (пользователя или группы). Другие настройки политики почтовых ящиков не могут повлиять на групп элементов. В прошлом, но была устранена с выпуском компонент политики хранения. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Что происходит с Скайп для бизнеса в Интернет и рабочих групп взаимодействия чаты — они влияет на политики хранения?

Да, Скайп для бизнеса в Интернет и группами взаимодействия чаты работает так же, как. После Скайп для бизнеса беседа переходит в группы, он становится сообщения в потоке чата групп и получает ingested в соответствующий почтовый ящик. Так же поток works – политики удаления группы приведет к удалению этих сообщений из потока команд. Тем не менее если журнал бесед для включено Скайп для бизнеса в Интернет и из Скайп для бизнеса в Интернет на стороне клиента тем, сохраняются в почтовый ящик, эти данные чата не обрабатывается политику хранения групп.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Можно делать их по безопасности & центре соответствия требованиям командлеты? Что следует использовать? 

Абсолютно. Можно создать политики хранения групп с помощью [командлетов безопасности и соответствия требованиям центр Powershell]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Помните, что эти не командлеты Exchange Online. Ниже перечислены командлеты, которые мы создали для групп. Они следуйте существующей Номенклатурный и стиль сегодня доступных командлетов хранения в центр соответствия требованиям и безопасности.

|Политики|Правила|
|---|---|
|[Новый TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Новый TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[SET-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [SET-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>При наличии нескольких политик хранения для групп с различной длительности, какой из них wins?

Мы следуйте [принципы политики хранения](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423), и мы рекомендуем выполнить слишком. Ответ — это: 
-   Сохранение всегда wins через удаления
-   Всегда длительный период хранения wins
-   Явное включение wins через неявных включения с точки зрения расположения
-   Минимальная удаления периода wins
