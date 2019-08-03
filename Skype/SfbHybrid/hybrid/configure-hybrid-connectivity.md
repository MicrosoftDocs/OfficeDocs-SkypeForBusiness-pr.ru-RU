---
title: Настройка гибридного подключения | Развертывание Skype для бизнеса Server 2019 Connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по внедрению гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online.
ms.openlocfilehash: ab7fb32c16e57e554c702a7b0f29ba350c1eedbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160703"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Настройка гибридного подключения между Skype для бизнеса Server и Office 365

**Сводка:** В этом разделе рассказывается, как настроить гибридное подключение между Skype для бизнеса Server и Teams и Skype для бизнеса Online.  Гибридное подключение позволяет вам перемещать локальных пользователей в Teams или Skype для бизнеса Online и позволяет пользователям использовать облачные службы.
  
Перед выполнением действий, описанных в этом разделе, необходимо ознакомиться со статьей " [планирование гибридного подключения между Skype для бизнеса Server и Office 365](plan-hybrid-connectivity.md)".
  
В следующей таблице перечислены задачи, необходимые для настройки подключения к гибридной сети Skype для бизнеса, а также приведены ссылки на соответствующие статьи для получения дополнительных сведений.
  
|Шаг|Описание|
|:-----|:-----|
|Создание учетной записи клиента для Office 365   <br/> |Узнайте о Office 365 в [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Чтобы убедиться, что ваша среда готова к работе с Office 365, ознакомьтесь с [требованиями к системе](https://products.office.com/en-US/office-system-requirements).  <br/> Подробнее о настройке Office 365 вы найдете в статье [Начало работы с office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Добавление домена в клиент Office 365 и проверка прав собственности  <br/> | Вам необходимо добавить домен в клиент Office 365 и затем проверить домен в Office 365. Эти действия предназначены для проверки прав владения доменом. <br/> Чтобы добавить свой домен в клиент Office 365, выполните действия, описанные в разделе [Добавление домена в office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Настройка синхронизации Active Directory  <br/> |Синхронизация Active Directory обеспечивает непрерывную синхронизацию локальной службы каталогов Active Directory и Office 365. Это позволяет создавать синхронизированные версии каждой учетной записи пользователя и группы.  <br/> <br> **Важно!** Необходимо синхронизировать учетные записи AD для всех пользователей Skype для бизнеса в Организации между локальными и оперативными развертываниями, даже если пользователи не перемещаются в Teams или Skype для бизнеса Online. Если вы не синхронизируете всех пользователей, связь между локальными и сетевыми пользователями в Организации может работать неправильно. Дополнительные сведения см. в статье [Настройка Azure AD Connect для гибридных сред](configure-azure-ad-connect.md).         |
| Настройка гибридной среды Skype для бизнеса | Необходимо выполнить три основных действия. <br><br> 1. Настройте локальную среду для Федерации с Office 365. <br> 2. Настройте локальную среду для доверия к Office 365 и включите общее адресное пространство SIP с помощью Office 365.<br> 3. Включите общее адресное пространство SIP в клиенте Office 365. <br><br> Кроме того, если у вас есть локальная служба Exchange, вам может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online. <br> <br>Дополнительные сведения можно найти в статье [Настройка гибридной среды Skype для бизнеса](configure-federation-with-skype-for-business-online.md).
|Перемещение пилотных пользователей  <br/> |После выполнения действий по подготовке и настройке среды для Teams или Skype для бизнеса Online вы можете переместить пилотных пользователей в свой клиент Office 365. Дополнительную информацию можно узнать в статье [Перемещение пользователей из локальной сети в Skype для бизнеса Online](move-users-from-on-premises-to-skype-for-business-online.md) и [Перемещение пользователей из локальной сети в](move-users-from-on-premises-to-Teams.md)Microsoft Teams.  <br/> |