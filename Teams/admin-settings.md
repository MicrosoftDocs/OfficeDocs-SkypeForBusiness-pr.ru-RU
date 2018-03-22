---
title: Параметры администратора для приложений в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Сведения о том, как разрешить и включить приложения в Microsoft Teams, включая загрузку неопубликованных внешних приложений.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58fb8598f8e63aa3e8abc943dcffde64452da462
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Параметры администратора для приложений в Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Приложения — это предоставляемые сторонними службами вкладки, соединители, боты или любое их сочетание. Центр администрирования Office 365 позволяет настроить политики администрирования Microsoft Teams, которые определяют разрешенные внешние сторонние приложения. В них вы можете указать, какие программы следует разрешать, а какие — блокировать, как работать с новыми внешними приложениями и можно ли загружать неопубликованные приложения.

> [!NOTE]
> Настройки администрирования для приложений Teams находятся в центре администрирования Office 365 в разделе **Параметры**  >  **Службы и надстройки** > **Microsoft Teams**. Если вы вошли как администратор Office 365, воспользуйтесь ссылкой
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Дополнительные сведения о настройках администрирования приложений см. в следующем видео. 
 
|  |  |
|---------|---------|
| Настройка приложений в Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Разрешение внешних приложений в Microsoft Teams

По умолчанию параметр **Allow external apps in Microsoft Teams** (Разрешить внешние приложения в Microsoft Teams) включен и выбраны все приложения.  Если отключить этот параметр, все внешние сторонние приложения будут запрещены. 

## <a name="enable-new-external-apps-by-default"></a>Включение новых внешних приложений по умолчанию

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Рекомендация: управление внешними приложениями по отдельности 
 
Чтобы включить определенные приложения и отключить другие, отключите параметр **Allow sideloading of external apps** (Разрешить загрузку неопубликованных внешних приложений). Затем отключите те приложения, доступ к которым следует запретить. Необязательно: отключите параметр **Enable new external apps by default** (Включить новые внешние приложения по умолчанию), если вы хотите контролировать новые приложения. 

Если этот параметр включен, пользователи могут активировать новые приложения сразу после их добавления в каталог приложений Microsoft Teams. Чтобы открыть каталог приложений Microsoft Teams, выберите пункт **Магазин** в нижней части Microsoft Teams и щелкните **Приложения**. Если вы хотите контролировать, какие будут доступны приложения, отключите этот параметр. В этом случае не забывайте периодически просматривать новые приложения, чтобы ваша организация не пропустила появление новых интересных программ. 

Загрузка неопубликованного приложения — это возможность добавить приложение в Microsoft Teams, непосредственно отправив в команду ZIP-файл. Загрузка неопубликованного приложения позволяет тестировать приложение в процессе его разработки. Она также позволяет создать приложение только для внутреннего пользования и поделиться им с командой, не отправляя программу в каталог приложений Microsoft Teams в Магазине Office. 

Загружать неопубликованные приложения в Microsoft Teams могут только владельцы команд или участники с соответствующими разрешениями.  

![Снимок экрана с расширенной раздел приложения в параметры на уровне клиента.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)


## <a name="creating-and-uploading-app-packages"></a>Создание и отправка пакетов приложений 

Дополнительные сведения о приложениях: [Develop apps for Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)(Разработка приложений для Microsoft Teams). 



