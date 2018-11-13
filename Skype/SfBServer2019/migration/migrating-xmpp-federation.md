---
title: Перенос федерации XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Предыдущие версии предоставляются Расширяемые системы обмена сообщениями и сведениями о присутствии протокола XMPP шлюз, который может быть развернуты как отдельный сервер роль разрешить федеративные отношения с развертываниями XMPP. Функциональные возможности XMPP больше не доступен и не рекомендуемые для использования в Скайп для Business Server 2019. Если вы хотите продолжить работу функциональные возможности XMPP, который можно availed в coexitence среды с устаревших версий (Скайп для Business Server 2015 и Lync Server 2013). Функциональные возможности XMPP устанавливается на две части: как XMPP прокси-сервера, на котором выполняется на устаревший пограничный сервер и шлюза XMPP, который выполняется на устаревшего сервера переднего плана.'
ms.openlocfilehash: 752d563796d7c8a5ba4bb7f98f22f8bef40822b4
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294474"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="f5d1f-106">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="f5d1f-106">Migrating XMPP federation</span></span>

<span data-ttu-id="f5d1f-107">Предыдущие версии предоставляются Расширяемые системы обмена сообщениями и сведениями о присутствии протокола XMPP шлюз, который может быть развернуты как отдельный сервер роль разрешить федеративные отношения с развертываниями XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="f5d1f-108">Функция XMPP больше недоступен и удален в Скайп Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="f5d1f-109">Если вы хотите продолжить работу функциональные возможности XMPP, можно сделать в среде сосуществования с устаревших версий (Скайп Business Server 2015 и Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="f5d1f-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="f5d1f-110">Функциональные возможности XMPP устанавливается на две части: как XMPP прокси-сервера, на котором выполняется на устаревший пограничный сервер и шлюза XMPP, который выполняется на устаревшего сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="f5d1f-111">С точки зрения переноса пользователей, желающих доступный компонента XMPP должны оставаться в устаревшем сервере и не должны будут перенесены в Скайп для пула Business Server 2019, но продолжить использовать устаревший шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="f5d1f-112">Это возможно только в том случае, когда федеративного партнера XMPP настроен в Скайп Business Server 2015 или Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="f5d1f-113">Следует не миграции устаревшего пограничного сервера на Скайп для Business Server 2019 чтобы продолжить работу функциональные возможности XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="f5d1f-114">Тем не менее могут иметь совместная работа устаревшего пограничного сервера (с прокси-сервера XMPP) и Скайп для бизнеса 2019 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

