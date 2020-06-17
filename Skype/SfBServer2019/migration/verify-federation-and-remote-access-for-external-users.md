---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После переноса маршрута Федерации на пограничный сервер Skype для бизнеса Server 2019 необходимо выполнить некоторые функциональные тесты, чтобы убедиться, что Федерация работает должным образом. В тесты для внешних пользователей должны включаться все типы пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751671"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="5fc6c-104">Проверка федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="5fc6c-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="5fc6c-105">После переноса маршрута Федерации на пограничный сервер Skype для бизнеса Server 2019 необходимо выполнить некоторые функциональные тесты, чтобы убедиться, что Федерация работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="5fc6c-106">В тесты для внешних пользователей должны включаться все типы пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="5fc6c-107">Проверка возможности подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="5fc6c-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="5fc6c-108">Пользователи, по крайней мере, один федеративный домен, внутренний пользователь в Skype для бизнеса Server 2019 и пользователь в устаревшей установке.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="5fc6c-109">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="5fc6c-110">Пользователи каждого общедоступного поставщика услуг обмена мгновенными сообщениями, поддерживаемого организацией (и для которого была выполнена подготовка), обмениваются данными с пользователем в Skype для бизнеса Server 2019 и пользователем устаревшей установки.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="5fc6c-111">Проверьте, что анонимные пользователи могут присоединиться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="5fc6c-112">Пользователь, размещенный в устаревшей установке и использующий удаленный доступ пользователей (вход в систему, я nЧтобы Lync Server/Skype для бизнеса за пределами интрасети, но не VPN) с пользователем в Skype для бизнеса Server 2019, и пользователь в устаревшей установке.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="5fc6c-113">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="5fc6c-114">Пользователь, размещенный в Skype для бизнеса Server 2019, использующий удаленный доступ пользователей (вход в Skype для бизнеса Server 2019 извне интрасети, но без VPN) с пользователем в Skype для бизнеса Server 2019, и пользователь в предыдущей установке.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="5fc6c-115">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="5fc6c-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

