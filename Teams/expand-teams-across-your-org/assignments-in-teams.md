---
title: Задания в Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Сведения об управлении назначениями в центре администрирования группами Майкрософт в группах для образовательных учреждений.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 263b9dda6929bd6956df803a33764634808cddf3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914025"
---
# <a name="assignments-in-teams-for-education"></a>Задания в Teams для образовательных учреждений

Назначения, задачи или единицы трудозатрат, назначенных участником группы или учебы в классе как часть изучение. Назначения можно создать в классе группами.

[Дополнительные сведения о назначениях](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Назначения в центре администрирования группами Майкрософт

С параметрами администрирования в центре администрирования группами Майкрософт можно преобразовать следующие функции включено или отключено для студентов и преподавателей вашей организации. Ниже приведены параметры, связанные с назначениями.

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Еженедельный дайджест опекуном электронной почты
Опекуном по электронной почте, еженедельно сообщений, отправляемых в родителей или опекунов учащихся. По электронной почте будут содержаться сведения о назначениях из предыдущей недели и предстоящие неделю и будут отправляться в выходные. Сообщения электронной почты должны быть обновлены с помощью компонента синхронизации данных School.

По умолчанию этот параметр отключен.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode — на основе блока платформа написания кода, реализующее науки компьютера для всех учащихся. 

Это продуктов сторонних производителей или служба, которая может быть собственный терминов и политику конфиденциальности. Вы несете ответственность за использование любого продуктов сторонних производителей и служб.

По умолчанию этот параметр отключен.

[Дополнительные сведения о MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin — это служба обнаружения plagiarism. Это продуктов сторонних производителей или служба, которая может быть собственный терминов и политику конфиденциальности. Вы несете ответственность за использование любого продуктов сторонних производителей и служб.

По умолчанию этот параметр отключен.

Чтобы успешно включить Turnitin для вашей организации, необходимо будет уже есть подписка Turnitin. Необходимо будет вводимых пользователем данных следующие дополнительные сведения, которые можно найти в консоль администрирования Turnitin:

  * _TurnitinApiKey_: это идентификатор GUID 32 символов, обнаруженных в консоли администрирования в области интеграции.
  * _TurnitinApiUrl_: это URL-адрес HTTPS Turnitin консоль администрирования.

Ниже приведены некоторые инструкции для получения этой информации.

TurnitinApiUrl — это адрес узла консоль администрирования.
![Поиск TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin1.png)

Перейдите на вкладку интеграции и добавьте интеграцию.
![Поиск TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin2.png)

TurnitinApiKey будет предоставлен вам после следуйте подсказкам. Этот ключ скопируйте и вставьте его в центре администрирования группами Майкрософт. 
![Поиск TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin3.png)

[Дополнительные сведения об интеграции между Turnitin и группами Майкрософт](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Дополнительные сведения о Turnitin](https://www.turnitin.com/)
