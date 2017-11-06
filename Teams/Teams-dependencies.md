---
title: "Зависимости Office 365 для Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Работа Microsoft Teams основана на Группах Office 365, SharePoint Online и OneDrive для бизнеса."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Зависимости Office 365 для Microsoft Teams
===========================================

Microsoft Teams использует Группы Office 365 для хранения сведений о членстве в командах и других свойств, например параметров классификации данных для команд. Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды. 

Служба Teams также использует SharePoint Online и OneDrive для бизнеса, чтобы хранить файлы и документы для бесед в каналах и чате. Кроме того, Teams использует Группы Office 365 для хранения сведений о членстве в командах и других свойств, например параметров классификации данных для команд. На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).
  
    
    
Чтобы обеспечить полноценный гостевой доступ в Teams, администраторам Office 365 следует выбрать значение **Включить** для следующих параметров:
  
    
    

- В SharePoint Online: **Only allow sharing with external users already in the directory (Разрешить общий доступ только с внешними пользователями, уже присутствующими в каталоге)**
    
    Дополнительные сведения см. в статье [Управление внешним общим доступом для среды SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- В Группах Office 365: **Let group owners add people outside the organization to groups (Разрешить владельцам добавлять в группы людей извне организации)**
    
    Дополнительные сведения см. в статье [Контроль гостевого доступа в Microsoft Teams](#controlguest).
  

Вы можете управлять параметрами внешних пользователей SharePoint Online для подключенного к Teams сайта группы. Дополнительные сведения см. в статье [Управление параметрами для сайта группы SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).