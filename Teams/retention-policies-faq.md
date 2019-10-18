---
title: 'Политики хранения Microsoft Teams: вопросы и ответы'
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Ответы на часто задаваемые вопросы о политиках хранения в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbeab6df377dd898b9c0d424288300ad7f01fbfc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569977"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Политики хранения Microsoft Teams: вопросы и ответы

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Какие типы политик можно настроить в политиках хранения и как они работают?

В центре безопасности &, когда вы настраиваете политику хранения, для Teams или для любой другой рабочей нагрузки, вы можете настроить два основных типа политик: 
- Сохранение: эти политики гарантируют, что данные будут сохраняться в течение определенного периода времени, независимо от того, что происходит в средствах конечного пользователя. Они гарантируют, что данные будут сохранены в соответствии с причинами соответствия требованиям, и они будут доступны в eDiscovery до истечения этого времени. По истечении этого времени политика может указать, нужно ли ничего делать или удалить данные. В Teams, если вы создаете политику сохранения в течение 7 лет, даже если конечные пользователи удаляют сообщения команды, эти сообщения по-прежнему сохраняются для обнаружения электронных данных в течение 7 лет.
- Удаление: эти политики гарантируют, что данные не являются ответственностью для вашей организации. После указанной длительности данные удаляются из всего необходимого хранилища в Teams. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Могут ли мы включать команды в политики Организации? 

Нет, в настоящее время нет. Вы должны создать конкретные политики для сообщений в чате и каналах команд с помощью строки расположения Teams или следующих командлетов teams: [New-теамсретентионкомплианцеполици](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-теамскомплианцеретентионруле](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Эти командлеты также получают и устанавливают версии.

### <a name="are-these-retention-policies-retroactive"></a>Неотложными ли эти политики хранения? 

Да, это не так. Если вы создаете политику хранения для удаления данных старше 60 дней, она удалит данные группы, созданные более 60 дней назад. 

### <a name="what-is-the-default-retention-policy"></a>Какова политика хранения по умолчанию? 

По умолчанию данные чата, каналы и файлов в Teams сохраняются постоянно. Пользователь может удалить что-либо, но в случае отсутствия политик хранения данные Teams всегда архивируются в почтовые ящики Exchange Online (пользователи и группы) и остаются там для обнаружения электронных данных. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Можно ли назначить набор пользователей или групп в политике? 

Да, это нужно сделать. В мастере создания политики на этапе расположений вы можете включить или исключить команды (**сообщения канала группы**) или пользователей (**Teams Chat**) и создать целевые политики для Организации. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>В чем заключается основное различие между строкой расположение группового почтового ящика и сообщениями канала группы в политиках хранения? 

Если вы используете строки группового почтового ящика и местоположения почтового ящика пользователя для Exchange Online, данные Teams удаляются из указанных почтовых ящиков. Тем не менее, данные удаляются только из почтового ящика. В нем не удаляются другие данные Teams, например служба чатов. Для правильного управления всеми группами данных рекомендуется использовать политики хранения Teams. Политика хранения Teams удаляет данные групп из всех местоположений хранилища: почтовые ящики, служба чата, клиенты Teams. 

Примечание. Запуск функции политик хранения для Teams гарантирует, что только политики Teams удаляют элементы Teams, хранящиеся в расположениях почтового ящика Exchange (пользователь или группа). Настройка других политик в почтовых ящиках не может повлиять на элементы Teams. Это было верно в прошлом, но было устранено с помощью функции "политики хранения". 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Что происходит с обсуждениями в Skype для бизнеса Online и Teams, – они влияют на политики хранения?

Да, Skype для бизнеса Online и беседы по взаимодействию в Teams работают одинаковым образом. После того как чат Skype для бизнеса Online поступает в Teams, он становится сообщением в потоке чата в Teams и получается из соответствующего почтового ящика. Так что один и тот же поток работает — политики удаления Teams будут удалять эти сообщения из потока команд. Тем не менее, если в Skype для бизнеса Online включена История бесед и на клиенте Skype для бизнеса Online они сохраняются в почтовом ящике, эти данные чата не обрабатываются политикой хранения в Teams.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Можно ли сделать это с помощью командлетов центра безопасности & соответствия требованиям? Что следует использовать? 

Позиционирование. Вы можете создавать политики хранения команд с помощью [командлетов PowerShell центра безопасности &]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Помните о том, что это не командлеты Exchange Online. Ниже указаны командлеты, созданные для Teams. Они поддерживайте существующую номенклатуру и стиль из командлетов хранения, доступных сегодня в центре безопасности & соответствия требованиям.

|Policy|Условия|
|---|---|
|[New-Теамсретентионкомплианцеполици](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-Теамсретентионкомплианцеруле](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-Теамсретентионкомплианцеполици](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-Теамсретентионкомплианцеруле](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-Теамсретентионкомплианцеполици](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-Теамсретентионкомплианцеруле](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-Теамсретентионкомплианцеполици](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-Теамсретентионкомплианцеруле](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Если вы используете несколько политик хранения для Teams с различной длительностью, один из которых является WINS?

Мы выполняйте [принципы политик хранения](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423), и мы рекомендуем вам. Короткий ответ: 
-   Сохранение всегда при удалении WINS
-   Наиболее продолжительный период хранения всегда WINS
-   Явное включение WINS для неявного включения в положениях местоположений
-   Самый короткий период удаления (WINS)
