---
title: Настройка гибридного подключения | Развертывание Skype для бизнеса Server 2019 подключения
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
description: Инструкции по реализации гибридного подключения между Skype для бизнеса Server и Teams.
ms.openlocfilehash: 1b1fee4fe513778433bff077ce23973e4bfc0d8a
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305943"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Настройка гибридного подключения между Skype для бизнеса Server и Teams

**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как настроить гибридную связь между Skype для бизнеса Server и Teams (или Skype для бизнеса Online до ее выхода на пенсию).  Гибридное подключение позволяет перемещать локального пользователя в Teams (или Skype для бизнеса Online) и позволяет пользователям использовать облачные службы.
  
Перед выполнением действий в этом разделе необходимо прочитать план гибридного подключения между Skype для бизнеса Server [и Teams](plan-hybrid-connectivity.md).
  
В следующей таблице перечислены задачи, необходимые для Skype для бизнеса гибридного подключения, а также ссылки на связанные статьи для получения дополнительных сведений.
  
|Шаг|Описание|
|:-----|:-----|
|Создание учетной записи клиента для Microsoft 365   <br/> |Узнайте о Microsoft 365 в [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Чтобы убедиться, что среда готова к Microsoft 365, см. в статью [System Requirements.](https://products.office.com/office-system-requirements)  <br/> Сведения о настройке Microsoft 365 см. в материале [Getting Started with Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|Добавление домена в организацию Microsoft 365 и проверка права собственности  <br/> | Необходимо добавить домен в организацию Microsoft 365, а затем выполните действия по проверке домена с помощью Microsoft 365. Эти действия предназначены для проверки прав владения доменом. <br/> Чтобы добавить домен в организацию Microsoft 365, выполните действия, описанные в добавлении домена [в Microsoft 365.](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|Настройка синхронизации Active Directory  <br/> |Синхронизация Active Directory обеспечивает непрерывное синхронизацию локального Active Directory с Microsoft 365. Это позволяет создавать синхронизированные версии каждой учетной записи и группы пользователей.  <br/> <br> **Важно:** Необходимо синхронизировать учетные записи AD для всех пользователей Skype для бизнеса организации между локальной и сетевой развертываниями, даже если пользователи не перемещаются в Teams (или Skype для бизнеса Online). Если вы не синхронизируете всех пользователей, связь между локальной и интернет-пользователями в вашей организации может работать не так, как ожидалось. Дополнительные сведения см. в Подключение Azure AD для [гибридных сред.](configure-azure-ad-connect.md)         |
| Настройка гибридной среды Skype для бизнеса | Необходимо выполнить три основных действия. <br><br> 1. Настройка локальной среды для федерации с помощью Microsoft 365. <br> 2. Настройте локальное окружение, чтобы доверять Microsoft 365 и включить совместное пространство адресов SIP с Microsoft 365.<br> 3. Включить общее пространство адресов SIP в Microsoft 365 организации. <br><br> Кроме того, если у вас есть локальная служба Exchange, вам может потребоваться настроить OAuth между локальной средой Exchange и средами Skype для бизнеса Online. <br> <br>Дополнительные сведения см. в [Skype для бизнеса hybrid.](configure-federation-with-skype-for-business-online.md)
|Перемещение пилотных пользователей  <br/> |После завершения действий по подготовке и настройке среды для Teams (или Skype для бизнеса Online) можно приступить к перемещению пилотных пользователей в организацию Microsoft 365. Дополнительные сведения см. в веб-сайте [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md) и Move users from on [premises to Skype для бизнеса Online.](move-users-from-on-premises-to-skype-for-business-online.md)  <br/> |
