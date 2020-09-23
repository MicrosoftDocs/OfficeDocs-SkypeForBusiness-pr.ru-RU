---
title: Управление политиками голосовой маршрутизации в Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Сведения о том, как создавать политики голосовой маршрутизации и управлять ими в Microsoft Teams.
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217660"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Управление политиками голосовой маршрутизации в Microsoft Teams

Если вы развернули [прямую маршрутизацию телефонной системы](direct-routing-landing-page.md) в своей организации, вы используете политики голосовой связи, позволяющие пользователям групп и Skype для бизнеса Online получать и звонить по телефонной сети общего пользования (PSTN) с помощью локальной инфраструктуры телефонной связи.

Политика маршрутизации голосовой связи — это контейнер для записей об использовании КТСОП. Вы можете создавать политики голосовой маршрутизации и управлять ими, переключаясь **на**  >  **политики маршрутизации голосовой голосовой связи** в центре администрирования Microsoft Teams или с помощью Windows PowerShell.

Вы можете использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики. Пользователи будут автоматически получать глобальную политику, если вы не создадите и не назначаете пользовательскую политику. Имейте в виду, что вы можете изменять параметры глобальной политики, но переименовывать и удалять их нельзя.

Важно знать, что назначение пользователю политики голосовой маршрутизации не позволяет им звонить по PSTN в Teams. Кроме того, вам необходимо включить прямую маршрутизацию на телефонную систему и выполнить другие действия по настройке. Дополнительные сведения можно найти в статье [Настройка прямого маршрута](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Создание настраиваемой политики голосовой маршрутизации

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Voice**  >  **политики маршрутизации голосовой голосовой связи**и нажмите кнопку **Добавить**.<br>
    ![Снимок экрана: страница "Добавление политики голосовой маршрутизации" в центре администрирования Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Введите имя и описание для политики.
3. В разделе **записи использования PSTN**щелкните **Добавить использование КТСОП**и выберите записи, которые вы хотите добавить. Если вам нужно создать новую запись использования КТСОП, нажмите кнопку **Добавить**.
4. Если вы добавили несколько записей PSTN Usage, расположите их в нужном порядке.
5. Когда все будет готово, нажмите кнопку **Применить**.
6. Нажмите кнопку **Сохранить**.

### <a name="using-powershell"></a>Использование PowerShell

Просмотреть раздел [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Изменение политики голосовой маршрутизации

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

Вы можете изменить глобальную политику или созданные вами пользовательские политики.

1. В левой области навигации центра администрирования Microsoft Teams **перейдите на вкладку**  >  **политики маршрутизации голосовой голосовой связи**.
2. Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.
3. Нажмите кнопку **Добавить/удалить записи использования PSTN**, внесите необходимые изменения и нажмите кнопку **сохранить**.

### <a name="using-powershell"></a>Использование PowerShell

Смотрите раздел [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Назначение настраиваемой политики голосовой маршрутизации пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Дополнительные сведения можно найти в разделе [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Статьи по теме

[Обзор PowerShell в Teams](teams-powershell-overview.md)

[Настройка маршрутизации голосовой связи для прямой маршрутизации](direct-routing-voice-routing.md)

[Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации](location-based-routing-enable.md)

[Назначение политик пользователям в Teams](assign-policies.md)
