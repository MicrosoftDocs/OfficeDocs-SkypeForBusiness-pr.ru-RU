---
title: Расширитель общих параметров внешних приложений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы изменить свойства доверенного сервера приложений, который уже определен, выполните указанные ниже действия.
ms.openlocfilehash: dffeb52ab1633a936a73cb2270a204d26ccf1056
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702174"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="7101f-103">Расширитель общих параметров внешних приложений</span><span class="sxs-lookup"><span data-stu-id="7101f-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="7101f-104">Чтобы изменить свойства доверенного сервера приложений, который уже определен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7101f-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="7101f-105">Существует два раздела, которые можно изменить.</span><span class="sxs-lookup"><span data-stu-id="7101f-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="7101f-106">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="7101f-106">General settings</span></span>
> 
> <span data-ttu-id="7101f-107">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="7101f-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="7101f-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="7101f-108">General Settings</span></span>

<span data-ttu-id="7101f-109">Вы можете изменить полное доменное имя (FQDN) для пула доверенных серверов приложений.</span><span class="sxs-lookup"><span data-stu-id="7101f-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="7101f-110">Измените имя FQDN пула.</span><span class="sxs-lookup"><span data-stu-id="7101f-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="7101f-111">Для новой записи должны существовать записи узла доменных имен (DNS) (A), прежде чем клиенты или серверы смогут подключиться к имени нового пула.</span><span class="sxs-lookup"><span data-stu-id="7101f-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="7101f-112">Выберите параметр **включить репликацию данных конфигурации в этот пул** , если вам необходима репликация данных конфигурации в этот пул.</span><span class="sxs-lookup"><span data-stu-id="7101f-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="7101f-113">Снимите флажок, если вы не хотите реплицировать данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7101f-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="7101f-114">Параметры следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="7101f-114">Next Hop Settings</span></span>

<span data-ttu-id="7101f-115">Вы можете задать сервер следующего прыжка для пула серверов приложений, выбрав на нем определенный пул переднего плана Enterprise Edition или стандартный сервер переднего плана из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7101f-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="7101f-116">Пул режиссера или режиссера не является допустимым выбором для надежного сервера приложений и не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="7101f-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="7101f-117">Нажмите кнопку **ОК** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="7101f-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="7101f-118">Для отмены изменений и закрытия страницы свойств нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="7101f-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

