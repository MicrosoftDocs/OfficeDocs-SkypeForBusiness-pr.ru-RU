---
title: Настройка гибридных подключений | Развертывание подключения Skype для бизнеса Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по реализации гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online.
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376752"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Настройка гибридного подключения между приложением Skype для бизнеса Server и Office 365

**Сводка:** В этом разделе вы узнаете, как настроить гибридное подключение между Skype для бизнеса Server и Teams или Skype для бизнеса Online.  Гибридное подключение позволяет переместить пользователей из локальной сети в Teams или Skype для бизнеса Online, а также использовать облачные службы.
  
Перед выполнением действий в этом разделе необходимо прочитать статью "Планирование гибридного подключения между Skype для бизнеса Server и [Office 365".](plan-hybrid-connectivity.md)
  
В следующей таблице перечислены задачи, необходимые для настройки гибридного подключения Skype для бизнеса, а также ссылки на связанные статьи для получения дополнительных сведений.
  
|Шаг|Описание|
|:-----|:-----|
|Создание учетной записи клиента для Office 365   <br/> |Узнайте об Office 365 в [Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> Чтобы убедиться, что ваша среда готова к Office 365, см. статью ["Системные требования".](https://products.office.com/office-system-requirements)  <br/> Подробные сведения о настройке Office 365 см. в сведениях о том, как начать работу [с Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|Добавление домена в организацию Office 365 и проверка владения  <br/> | Необходимо добавить домен в организацию Office 365, а затем проверить домен с помощью Office 365. Эти действия предназначены для проверки прав владения доменом. <br/> Чтобы добавить домен в организацию Office 365, выполните действия, описанные в описании добавления домена [в Office 365.](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|Настройка синхронизации Active Directory  <br/> |Синхронизация Active Directory обеспечивает непрерывную синхронизацию локальной службы каталогов Active Directory и Office 365. Это позволяет создавать синхронизированные версии каждой учетной записи пользователя и группы.  <br/> <br> **Важно!** Необходимо синхронизировать учетные записи AD для всех пользователей Skype для бизнеса в организации между локальной и сетевой развертываниями, даже если пользователи не перемещены в Teams или Skype для бизнеса Online. Если вы не синхронизируете всех пользователей, связь между локальной и интернет-пользователями в организации может работать не так, как ожидалось. Дополнительные сведения см. в настройке [Azure AD Connect для гибридных сред.](configure-azure-ad-connect.md)         |
| Настройка гибридной среды Skype для бизнеса | Необходимо выполнить три основных действия. <br><br> 1. Настройте свою локальной среду для федерации с Office 365. <br> 2. Настройте свою локальной среду так, чтобы она доверяла Office 365 и встроила общее адресное пространство SIP в Office 365.<br> 3. В enable shared SIP address space in your Office 365 organization. <br><br> Кроме того, если у вас есть локальная служба Exchange, вам может потребоваться настроить OAuth между локальной средой Exchange и средами Skype для бизнеса Online. <br> <br>Дополнительные сведения см. в [подстройке "Настройка гибридной конфигурации Skype для бизнеса".](configure-federation-with-skype-for-business-online.md)
|Перемещение пилотных пользователей  <br/> |После завершения действий по подготовке и настройке среды для Teams или Skype для бизнеса Online можно приступить к перемещению пилотных пользователей в организацию Office 365 в Интернете. Дополнительные сведения см. в подсети "Перемещение пользователей из локальной сети в Skype для бизнеса [Online"](move-users-from-on-premises-to-skype-for-business-online.md) и "Перемещение пользователей из локальной сети [в Teams".](move-users-from-on-premises-to-Teams.md)  <br/> |
