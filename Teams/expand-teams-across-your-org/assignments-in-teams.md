---
title: Задания в Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Сведения о том, как управлять заданиями в центре администрирования Microsoft Teams в Teams для образовательных учреждений.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1747075caecdbc4bcd0c83eb037682b023701799
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814778"
---
# <a name="assignments-in-teams-for-education"></a>Задания в Teams для образовательных учреждений

Назначения — это задачи или единицы работы, назначенные студенту или участнику команды в классе в рамках изучения. Вы можете создавать задания в рамках класса Teams.

[Дополнительные сведения о назначениях](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

 > [!Note]
 > Дополнительные сведения [можно найти в разделе функции группы по платформам](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) .

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Назначения в центре администрирования Microsoft Teams

С помощью параметров администратора в центре администрирования Microsoft Teams вы можете включать и отключать указанные ниже функции, чтобы быть доступными для учащихся и преподавателей в Организации. Ниже указаны параметры, связанные с назначениями.

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Еженедельная сводка по электронной почте опекунов

Сообщения в опекунах — это еженедельные сообщения, отправляемые в родителей и опекунах учащихся. В сообщениях электронной почты будут содержаться сведения о назначениях за предыдущую неделю и за неделю, и они будут отправлены по выходным. Сообщения электронной почты необходимо обновлять администраторами с помощью функции School Data Sync.

Этот параметр по умолчанию отключен.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode — это основанная на блоках платформа кодирования, благодаря которой компьютерному науку выдается жизнь для всех учащихся. 

MakeCode — это продукт Microsoft, в соответствии с [условиями использования](https://go.microsoft.com/fwlink/?LinkID=206977) и политикой [конфиденциальности](https://go.microsoft.com/fwlink/?LinkId=521839) корпорации Майкрософт.

Этот параметр по умолчанию отключен. Чтобы включить назначение MakeCode в Teams, в **центре администрирования Teams**перейдите в раздел **задания** и установите переключатель MakeCode в положение **вкл**. Нажмите кнопку **сохранить** и подождите, пока эти параметры не вступят в силу.

Дополнительные сведения о том, как работает эта функция, можно найти в этом [видеоролике](https://makecode.com/blog/teams/teams-assignments).

[Дополнительные сведения о MakeCode](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin — это служба обнаружения plagiarism. Это сторонний продукт или услуга, которым подпадают свои условия и правила конфиденциальности. Вы несете ответственность за использование каких-либо продуктов и услуг сторонних разработчиков.

Этот параметр по умолчанию отключен.

Чтобы успешно включить Turnitin для вашей организации, у вас должна быть уже подписка на Turnitin. Вам потребуется ввести следующие дополнительные сведения, которые можно найти на консоли администрирования Turnitin:

  * _TurnitinApiKey_: идентификатор GUID 32, который находится на консоли администрирования в разделе Интеграция.
  * _TurnitinApiUrl_: URL-адрес вашей консоли администратора Turnitin.

Вот несколько инструкций, которые помогут вам получить эти сведения.

TurnitinApiUrl — адрес узла консоли администрирования.
Образом. `https://your-tenant-name.turnitin.com`

На консоли администрирования вы можете создать интеграцию и ключ API, связанный с интеграцией.

В меню сбоку выберите пункт **Интеграция** , а затем — пункт **добавить интеграцию** и присвойте имя интеграции.
![Снимок экрана, демонстрирующий Добавление новой интеграции](./educationImages/Assignments_mopo_turnitin2.png)

TurnitinApiKey будет предоставлен вам после того, как вы подпишитесь на запросы. Скопируйте ключ API и вставьте его в центр администрирования Microsoft Teams.  Это единственный момент, когда вы можете просмотреть ключ.
![Снимок экрана, на котором показано, как копировать ключ API](./educationImages/Assignments_mopo_turnitin3.png)

При нажатии кнопки " **сохранить** " в центре администрирования для этого параметра подождите, пока эти параметры не вступят в силу.

Готовы приступить к работе с интеграцией Turnitin в Teams? Подпишитесь на [программу раннего доступа](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).
