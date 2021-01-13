---
title: Управление политиками маршрутинга голосовой почты в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как создавать политики маршрутинга голоса и управлять ими в Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802559"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Управление политиками маршрутинга голосовой почты в Microsoft Teams

При развертывании прямой маршрутизации телефонной системы в организации используются политики маршрутизации голосовой связи, позволяющие пользователям Teams и Skype для бизнеса Online принимать и звонить на телефонную сеть общего пользования (STN) с использованием локальной инфраструктуры телефонной связи. [](direct-routing-landing-page.md)

Политика голосовой маршрутки — это контейнер для записей об использовании ОКП. Чтобы создать политики маршрутинга голосовой почты и управлять ими, переходить к политикам маршрутики голосовой голосовой почты в Центре администрирования Microsoft Teams или с помощью   >   Windows PowerShell.

Вы можете использовать глобальную (по умолчанию в организации) политику или создать и назначить настраиваемые политики. Пользователи будут автоматически получать глобальную политику, если вы не создайте и не назначите ее. Помните, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.

Важно знать, что назначение пользователю политики маршрутинга голосовой почты не позволяет делать звонки по ННР в Teams. Кроме того, необходимо включить прямую маршрутацию телефонной системы и выполнить другие действия по настройке. Дополнительные узнать см. [в подстройке "Настройка прямой маршрутки".](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Создание настраиваемой политики маршрутинга голосовой почты

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам маршрутации голосовой голосовой почты и нажмите кнопку  >   **"Добавить".**<br>
    ![Снимок экрана: страница "Добавление политики маршрутинга голоса" в Центре администрирования Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Введите имя и описание для политики.
3. В **записях об использовании** ДНР нажмите кнопку "Добавить использование **ННР"** и выберите записи, которые нужно добавить. Если вам нужно создать запись использования ННР, нажмите кнопку **"Добавить".**
4. Если вы добавили несколько записей использования ННР, расположить их в нужном порядке.
5. Когда все будет готово, нажмите кнопку **"Применить".**
6. Щелкните **Сохранить**.

### <a name="using-powershell"></a>С помощью PowerShell

См. [new-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Изменение политики голосовой маршрутики

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам маршрутиации голосовой  >  **голосовой почты.**
2. Выберите политику, щелкнув слева от ее имени и нажав кнопку **"Изменить".**
3. Нажмите **кнопку "Добавить/удалить** записи использования ННР", внесем нужные изменения и нажмите кнопку **"Сохранить".**

### <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Назначение пользовательской политики маршрутинга голосовой почты пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

См. также [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Настройка голосовой маршрутии для прямой маршрутинга](direct-routing-voice-routing.md)

[Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации](location-based-routing-enable.md)

[Назначение политик пользователям в Teams](assign-policies.md)
