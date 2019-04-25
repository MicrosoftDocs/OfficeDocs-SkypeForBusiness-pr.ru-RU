---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После переноса федеративного маршрута для Скайп Business Server 2019 пограничного сервера, необходимо выполнить некоторые функциональных тестов, чтобы убедиться, что федерации работает, как ожидалось. Тесты доступа внешних пользователей должны охватывать все типы внешних пользователей, которые поддерживаются в организации, включая некоторые или все следующие.
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231352"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="20966-104">Проверка федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="20966-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="20966-105">После переноса федеративного маршрута для Скайп Business Server 2019 пограничного сервера, необходимо выполнить некоторые функциональных тестов, чтобы убедиться, что федерации работает, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="20966-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="20966-106">Тесты доступа внешних пользователей должны охватывать все типы внешних пользователей, которые поддерживаются в организации, включая некоторые или все следующие.</span><span class="sxs-lookup"><span data-stu-id="20966-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="20966-107">Проверка подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="20966-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="20966-108">Пользователи из по крайней мере один федеративного домена, внутренних пользователей на Скайп для Business Server 2019 и пользователем на устаревший установить.</span><span class="sxs-lookup"><span data-stu-id="20966-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="20966-109">Тестирование мгновенного обмена Мгновенными сообщениями, сведения о присутствии, аудио/видео (A / V) и рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="20966-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="20966-110">Пользователи каждого открытого поставщика службы обмена мгновенными Сообщениями, поддерживаемого в организации (и для которого была выполнена подготовка) устанавливать связь с пользователем на Скайп Business Server 2019 и пользователем на прежних версий install.</span><span class="sxs-lookup"><span data-stu-id="20966-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="20966-111">Убедитесь в том, что анонимные пользователи могут присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="20966-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="20966-112">Пользователь, размещенный в устаревший установить с помощью удаленного доступа пользователей (Ведение журнала i nДля того Lync Server/Скайп для бизнеса из за пределами интрасети, но без VPN) с пользователем на Скайп для Business Server 2019 и пользователя при установке прежних версий.</span><span class="sxs-lookup"><span data-stu-id="20966-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="20966-113">Проверить обмен мгновенными Сообщениями, присутствие, A / V и рабочему столу общего доступа.</span><span class="sxs-lookup"><span data-stu-id="20966-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="20966-114">Пользователь, размещенного на Скайп для 2019 Business Server, с помощью удаленного доступа пользователей (войти в программу Скайп для 2019 Business Server из за пределами интрасети, но без VPN) с пользователем на Скайп для Business Server 2019 и пользователем на устаревший установить.</span><span class="sxs-lookup"><span data-stu-id="20966-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="20966-115">Проверить обмен мгновенными Сообщениями, присутствие, A / V и рабочему столу общего доступа.</span><span class="sxs-lookup"><span data-stu-id="20966-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

