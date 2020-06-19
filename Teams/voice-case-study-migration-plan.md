---
title: Исследование успеха в голосовых сообщениях в Teams contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Исследование вариантов голосовой связи в среде Teams для международной Организации
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786090"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="67c16-103">Исследование успеха Contoso: план обновления Teams</span><span class="sxs-lookup"><span data-stu-id="67c16-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="67c16-104">При принятии решения о переходе с Skype для бизнеса на Teams компания Contoso хотела бы предоставить для конечных пользователей простой интерфейс переходов.</span><span class="sxs-lookup"><span data-stu-id="67c16-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="67c16-105">Вместо того чтобы переключаться между участниками в Teams, вы решили настроить гибридное подключение и использовать метод перекрытия для перемещения пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="67c16-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="67c16-106">Это позволило пользователям в Teams и Skype для бизнеса быть в локальной сети для совместного использования информации о присутствии и общении.</span><span class="sxs-lookup"><span data-stu-id="67c16-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="67c16-107">После того как пользователи вводили пилотный проект для телефонной системы, они были перемещены в режим "только для Teams".</span><span class="sxs-lookup"><span data-stu-id="67c16-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="67c16-108">Для ознакомления с основными понятиями, посвященными обновлению, методам и режимам, компания Contoso прочитала следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="67c16-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="67c16-109">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67c16-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="67c16-110">Переход со Skype для бизнеса на Teams</span><span class="sxs-lookup"><span data-stu-id="67c16-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="67c16-111">Руководство по миграции и взаимодействию</span><span class="sxs-lookup"><span data-stu-id="67c16-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="67c16-112">Contoso также посетил сеанс Ignite 2019, [разрабатывая свой путь из Skype для бизнеса в Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="67c16-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="67c16-113">Сведения о том, что Contoso узнали:</span><span class="sxs-lookup"><span data-stu-id="67c16-113">Contoso learned about:</span></span>

- <span data-ttu-id="67c16-114">Основные понятия, такие как взаимодействие, интеграция и поведение обновления</span><span class="sxs-lookup"><span data-stu-id="67c16-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="67c16-115">Режимы сосуществования и управление на основе TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="67c16-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="67c16-116">Взаимодействие с пользователем:</span><span class="sxs-lookup"><span data-stu-id="67c16-116">End user experience for:</span></span> 

  - <span data-ttu-id="67c16-117">Чат и звонки</span><span class="sxs-lookup"><span data-stu-id="67c16-117">Chat and Calling</span></span> 

  - <span data-ttu-id="67c16-118">Планирование собраний</span><span class="sxs-lookup"><span data-stu-id="67c16-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="67c16-119">Доступность функций совместной работы в клиентах Teams</span><span class="sxs-lookup"><span data-stu-id="67c16-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="67c16-120">Для планирования и настройки гибридного подключения сначала необходимо переместить локальную среду в облако, план чтения Contoso для [гибридного подключения](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) и [настроить гибридное подключение](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) , чтобы понять, как это сделать:</span><span class="sxs-lookup"><span data-stu-id="67c16-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="67c16-121">Настройте локальную службу среды на Федерацию с Office 365.</span><span class="sxs-lookup"><span data-stu-id="67c16-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="67c16-122">Настройка локальной среды для доверия к Office 365 и включение общего пространства адресов SIP с помощью Office 365</span><span class="sxs-lookup"><span data-stu-id="67c16-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="67c16-123">Включите общее адресное пространство SIP в своем клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="67c16-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="67c16-124">Использование режима "острова островов" во время технического проекта.</span><span class="sxs-lookup"><span data-stu-id="67c16-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="67c16-125">Переключение пользователей в режим TeamsOnly после включения пользователя для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="67c16-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="67c16-126">Для тарифного плана и прямой маршрутизации требуется режим TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="67c16-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
