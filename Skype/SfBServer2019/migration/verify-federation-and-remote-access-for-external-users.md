---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После того как вы перейдете на сервер пограничного сервера Skype для бизнеса Server 2019, необходимо выполнить несколько функциональных тестов, чтобы убедиться, что она работает должным образом. Для проверки внешнего доступа пользователей следует включить все типы внешних пользователей, которые поддерживаются вашей организацией, в том числе любые из указанных ниже элементов.
ms.openlocfilehash: ea17cbc8643d864f464da8e8a582191504970059
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243770"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="a3111-104">Проверка федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="a3111-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="a3111-105">После того как вы перейдете на сервер пограничного сервера Skype для бизнеса Server 2019, необходимо выполнить несколько функциональных тестов, чтобы убедиться, что она работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="a3111-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="a3111-106">Для проверки внешнего доступа пользователей следует включить все типы внешних пользователей, которые поддерживаются вашей организацией, в том числе любые из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="a3111-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="a3111-107">Проверка подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="a3111-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="a3111-108">Пользователи, у которых есть хотя бы один федеративный домен, внутренний пользователь в Skype для бизнеса Server 2019 и пользователь в установленной версии.</span><span class="sxs-lookup"><span data-stu-id="a3111-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a3111-109">Протестируйте обмен мгновенными сообщениями, присутствие, звук и видео (A/V) и общий доступ к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="a3111-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="a3111-110">Пользователи всех общедоступных служб обмена мгновенными сообщениями, которые поддерживаются вашей организацией (и для которых была выполнена подготовка) взаимодействия с пользователем в Skype для бизнеса Server 2019 и пользователем установленной версии.</span><span class="sxs-lookup"><span data-stu-id="a3111-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="a3111-111">Убедитесь в том, что анонимные пользователи смогут присоединиться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="a3111-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="a3111-112">Пользователь, размещенный в устаревшей установке и использующий удаленный доступ (ведение журнала, сервер Microsoft Lync Server/Skype для бизнеса за пределами интрасети, но не VPN) с пользователем в Skype для бизнеса Server 2019 и пользователем установленной версии.</span><span class="sxs-lookup"><span data-stu-id="a3111-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a3111-113">Проверка обмена мгновенными сообщениями, сведений о присутствии, а/V и совместном использовании рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="a3111-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="a3111-114">Пользователь, размещенный в Skype для бизнеса Server 2019, использующий удаленный доступ пользователей (вход в Skype для бизнеса Server 2019 из-за пределов интрасети, но не VPN) с пользователем в Skype для бизнеса Server 2019 и пользователем в устаревшей установке.</span><span class="sxs-lookup"><span data-stu-id="a3111-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a3111-115">Проверка обмена мгновенными сообщениями, сведений о присутствии, а/V и совместном использовании рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="a3111-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

