---
title: Adobe Acrobat в качестве средства просмотра PDF по умолчанию в Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Узнайте, как настроить Adobe Acrobat в качестве средства просмотра PDF-файлов по умолчанию для просмотра и редактирования PDF-файлов в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4776b2928ee734c1b37856e44d184c53bfc0dd90
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251902"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Установка Adobe Acrobat в качестве средства просмотра PDF-файлов по умолчанию в Майкрософт Teams

Администратор может настроить Adobe Acrobat в качестве приложения по умолчанию для просмотра и редактирования PDF-файлов в Microsoft Teams. Конечные пользователи могут просматривать PDF-файлы и выполнять поиск в ней. Пользователи также могут бесплатно комментировать PDF-файлы и примечать их после входа.

Чтобы настроить приложение Adobe Acrobat в качестве обработчика по умолчанию для PDF-файлов в клиенте, выполните следующие действия в качестве необходимых условий:

* [Разрешить приложение Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Установите приложение Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Разрешить приложение Adobe Acrobat в клиенте

Чтобы настроить приложение в качестве средства просмотра PDF по умолчанию, убедитесь, что вы [разрешили использовать стороннее приложение](manage-apps.md#manage-org-wide-app-settings) в клиенте. Затем следуйте приведенным ниже инструкциям, чтобы настроить Adobe Acrobat в качестве приложения по умолчанию для PDF-файлов.

1. Войдите в Центр администрирования Teams и получите доступ к **приложению** >  Teams **[Управление приложениями](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Найдите приложение Adobe Acrobat и выберите его. Откроется страница сведений о приложении.

1. Перейдите на вкладку **Разрешения** , а затем выберите **Проверить разрешение**.

   :::image type="content" source="media/permission-policy.png" alt-text="Снимок экрана разрешения приложения в центре администрирования Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Выберите **Принять**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Установка приложения Adobe Acrobat для всех пользователей

Чтобы назначить и сделать приложение Adobe Acrobat доступным для всех пользователей, выполните следующие действия.

1. В Центре администрирования Teams перейдите в **приложение Teams** > [**Настроить политики**](https://admin.teams.microsoft.com/policies/app-setup).

1. На вкладке **Управление политиками** выберите **Глобально (по умолчанию для всей организации)** и нажмите кнопку **Редактировать**.

   :::image type="content" source="media/setup-policies.png" alt-text="Снимок экрана: политики настройки для приложения Adobe Acrobat в центре администрирования Teams.":::

1. В разделе "Установленные приложения" выберите **Добавить приложения**.

1. Найдите **Adobe Acrobat**, выберите **Добавить** рядом с названием приложения, а затем выберите **Добавить**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Снимок экрана, на котором показано, как добавить приложение Adobe Acrobat для всех пользователей." lightbox="media/add-adobe-acrobat-app.png":::

1. Нажмите **Сохранить**.

После выбора параметра "Сохранить" Teams использует приложение Adobe Acrobat в качестве обработчика файлов по умолчанию для PDF-файлов.

Если вы хотите выборочно разрешить приложение Adobe Acrobat для нескольких пользователей или группы, используйте [политики разрешений приложений](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

Узнайте нижеследующую информацию об этой функции:

* После настройки политики обычно [требуется несколько часов](teams-app-setup-policies.md#considerations-and-limitations) , чтобы приложение стало доступным для пользователей.
* Собственный интерфейс PDF приложения Teams доступен для просмотра PDF-файлов, закрепленных в каналах в виде вкладки и доступных в приложении "Назначения".
* Adobe Acrobat в качестве средства просмотра PDF-файлов по умолчанию в Teams работает только на настольных компьютерах и веб-клиентах. Не поддерживается в мобильном клиенте.
* Пользователям требуется план Adobe Acrobat для использования таких премиум-средств, как "Экспорт PDF", "Упорядочивание страниц", "Объединение файлов", "Сжатие PDF" и "Защита PDF".
* Чтобы удалить приложение, конечные пользователи могут удалить приложение из своего клиента Teams. Администратор можно удалить приложение Adobe Acrobat с помощью политики установки.
* Если вы заблокируйте приложение Adobe Acrobat, удалите приложение из политики установки. Это гарантирует, что конечный пользователь вернется к использованию собственного средства просмотра файлов PDF.
* Если вы столкнулись с проблемами при входе в приложение Adobe Acrobat в классическом клиенте Teams, используйте [Teams в браузере](https://teams.microsoft.com/) для входа.
* Вход в бесплатную [учетную запись Adobe](https://acrobat.adobe.com/us/en/) необходим для комментариев или создания примечаний к PDF-файлам.
