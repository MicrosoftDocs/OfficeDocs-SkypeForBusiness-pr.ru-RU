---
title: Расширитель внешнего приложения общих параметров
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Чтобы изменить свойства сервера доверенных приложений, который уже был определен, выполните следующие действия.
ms.openlocfilehash: 4509b0c106c62391b9696acb94aec37861f8efe0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998822"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="af7be-103">Расширитель внешнего приложения общих параметров</span><span class="sxs-lookup"><span data-stu-id="af7be-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="af7be-104">Чтобы изменить свойства сервера доверенных приложений, который уже был определен, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="af7be-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="af7be-105">Существует два раздела, которые можно изменить.</span><span class="sxs-lookup"><span data-stu-id="af7be-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="af7be-106">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="af7be-106">General settings</span></span>
    
> <span data-ttu-id="af7be-107">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="af7be-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="af7be-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="af7be-108">General Settings</span></span>

<span data-ttu-id="af7be-109">Вы можете изменить текущее полное доменное имя (FQDN) для пула сервера доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="af7be-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="af7be-110">Измените имя полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="af7be-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="af7be-111">Записи узлов (A) доменных имен (DNS) должна существовать для новой записи, прежде чем клиентов или серверов может подключаться к новое имя группы.</span><span class="sxs-lookup"><span data-stu-id="af7be-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="af7be-112">Если необходимо иметь для этого пула репликацию данных конфигурации, установите флажок **Включить репликацию данных конфигурации в этот пул** .</span><span class="sxs-lookup"><span data-stu-id="af7be-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="af7be-113">Снимите флажок, если необходимо реплицировать данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af7be-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="af7be-114">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="af7be-114">Next Hop Settings</span></span>

<span data-ttu-id="af7be-115">Можно указать сервера следующего прыжка пула сервера доверенных приложений, выбрав определенного пула переднего плана Enterprise Edition или Standard Edition сервера переднего плана в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="af7be-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="af7be-116">Директор или директора пула не является допустимым выбора для следующего прыжка сервера доверенных приложений и не будет отображаться в списке.</span><span class="sxs-lookup"><span data-stu-id="af7be-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="af7be-117">Нажмите **кнопку ОК** , чтобы принять и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="af7be-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="af7be-118">Для отмены изменений и закрытия страницы свойств нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="af7be-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

