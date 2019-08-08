---
title: Переход на Teams с гибридного или локального развертывания Skype для бизнеса — Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Рекомендации по переходу на Teams из гибридного или локального развертывания Skype для бизнеса.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 873e15e5b1f64e82889bfda6fa30c5b9394dcf3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235877"
---
![Обновление схемы поездки, акцент на развертывании и реализации] (media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")

Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению. Перед продолжением убедитесь, что выполнены следующие действия:

-   [Вовлеченные заинтересованные лица в проект](upgrade-enlist-stakeholders.md)
-   [Определение области охвата проекта](https://aka.ms/SkypetoTeams-Scope)
-   [Сосуществование и взаимодействие Skype для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
-   [Выбрано путешествие с обновлением](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Подготовка среды](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Подготовка Организации](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Пробные испытания](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Переход на Teams из гибридного или локального развертывания Skype для бизнеса

Следуйте указаниям, приведенным в этой статье, если вы разработали Skype для бизнеса или Microsoft Lync в локальной среде, и ваша организация хочет выборочно перейти на Teams, используя несколько режимов сосуществования или все. Первый этап — это настройка гибридной связи с вашим клиентом Office 365, а затем перемещение пользователей в Skype для бизнеса Online и назначение им соответствующего режима сосуществования и обновления. 

> [!IMPORTANT]
> Skype для бизнеса Online будет прекращен до 31 июля 2021 г., после чего он больше не будет доступен или поддерживаться. Чтобы повысить эффективность реализации льготы и убедиться в том, что в вашей организации установлено правильное время для внедрения вашего обновления, мы рекомендуем начать путешествие в Microsoft Teams уже сегодня. Помните о том, что успешное обновление ориентировано на техническую и пользовательскую готовность, поэтому не забудьте использовать руководство для навигации в Microsoft Teams.

## <a name="step-1-deploy-hybrid-connectivity"></a>Действие 1: развертывание гибридного подключения 

Ключевым условием для обновления пользователей до Teams является развертывание гибридного подключения. Это может включать развертывание новых внешних подключений для существующего развертывания Skype для бизнеса или Lync, а также просто настройку гибридного отношения с вашим клиентом Office 365. 

Дополнительные сведения можно найти в разделе [развертывание гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Шаг 2: перемещение пользователей в Skype для бизнеса Online 

После того как вы закончите развертывание гибридной конфигурации, перенесите пользователей в Skype для бизнеса Online. 

Дополнительные сведения можно найти в разделе [Перемещение пользователей из локальной сети в Skype для бизнеса Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Шаг 3: назначение режима сосуществования и обновления

После того как вы перенесли пользователей в Skype для бизнеса Online, вы можете назначить им режим совместного существования, основываясь на пути обновления, который выбрала ваша организация. Дополнительные сведения можно найти [в статье Настройка параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [теамсупградеполици: управление миграцией и](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)сосуществованием.

> [!NOTE]
> С помощью Skype для бизнеса Server 2019 и будущего накопительного обновления для Skype для бизнеса Server 2015 вы сможете выполнить шаг 2 (перемещение пользователей в Skype для бизнеса Online) и шаг 3 (обновление пользователей до Teams). Дополнительные сведения будут предоставлены после выпуска Skype для бизнеса Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Обновление телефонной системы и команды

Если вы переносите гибридное развертывание Skype для бизнеса в телефонную систему с помощью планов звонков, а Microsoft является поставщиком услуг коммутируемой телефонной сети (PSTN) и предполагает, что вы выполнили перенос номера телефона, то после обновления пользователей В Teams будут автоматически перенесены входящие звонки через PSTN в Teams.

Если тарифные планы недоступны, вам нужно перевести свое развертывание в корпоративную типографию на прямую маршрутизацию Microsoft Phone System. Чтобы обновить пользователей до Teams, ознакомьтесь с [дополнительными сведениями о прямой маршрутизации для телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).
