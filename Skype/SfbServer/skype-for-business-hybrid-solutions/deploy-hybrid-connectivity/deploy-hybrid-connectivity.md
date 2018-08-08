---
title: Развертывание гибридных подключений между Skype для бизнеса Server и Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: Краткое содержание. В этом разделе приводятся сведения о развертывании гибридных подключений между Skype для бизнеса Server и Skype для бизнеса Online.
ms.openlocfilehash: d2f2792f46f50b8b4889a4659993bb4fa22dcbc0
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "21708341"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Развертывание гибридных подключений между Skype для бизнеса Server и Skype для бизнеса Online
 
**Краткое содержание**. В этом разделе приводятся сведения о развертывании гибридных подключений между Skype для бизнеса Server и Skype для бизнеса Online.
  
Перед выполнением действия, описанные в этом разделе, необходимо ознакомиться [Планирование гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
  
Гибридного подключения между Скайп для Business Server и Скайп для бизнеса в Интернет означает, что пользователи домен, например contoso.com, разделены между с помощью Скайп для Business Server локально и Скайп для бизнеса в Интернет. Некоторые пользователи домена размещаются в локальной среде, а другие — в облачной. 
  
В следующей таблице перечислены действия, необходимые для подготовки среды для гибридного развертывания с использованием Скайп для бизнеса в Интернет и Microsoft Office 365. 
  
|**Шаг**|**Описание**|
|:-----|:-----|
|Создание учетной записи клиента Office 365 и включение Скайп для бизнеса в Интернет  <br/> |Сведения об Office 365 и Скайп для бизнеса в Интернете в [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Чтобы убедиться в том, что среде готова для Office 365, в разделе [Требования к системе](https://products.office.com/en-US/office-system-requirements).  <br/> Для получения дополнительных сведений о настройке Office 365 видеть [Приступая к работе с Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Добавление домена в клиент Office 365 и проверка собственности  <br/> | Добавление домена в клиент Office 365 и затем следуйте инструкциям для проверки домена в Office 365. Это подтверждает, что вы являетесь владельца домена. <br/> Чтобы добавить домен в клиент Office 365, выполните действия, описанные на [странице Добавление домена в Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Подготовка к синхронизации службы каталогов Active Directory  <br/> |Синхронизация Active Directory сохраняет Active Directory локальной постоянно синхронизирован с Office 365. Это позволяет вам создать синхронизируются версий каждой учетной записи пользователя и группы, а также включает глобальных адресов синхронизации глобального списка адресов из локальной среды Microsoft Exchange Server в Microsoft Exchange Online. Для получения дополнительных сведений см [Средств интеграции каталогов](https://go.microsoft.com/fwlink/p/?LinkId=530320).  <br/>  **Внимание!** Необходимо синхронизировать учетные записи AD для всех Скайп для бизнес-пользователей в вашей организации между локальной и online развертываний даже в том случае, если пользователи не перемещается в Скайп для бизнеса в Интернет. Если синхронизированы не все пользователи, возможны нарушения связи между пользователями локального и сетевого развертываний.           |
|Перемещение пробных пользователей  <br/> |После завершения действия по подготовке и настройке среды для Скайп для бизнеса в Интернет, можно начать перемещение пилотных пользователей в вашей сети клиента Office 365. В разделе [Перемещение пользователей из локально на Скайп для бизнеса в Интернет](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |
