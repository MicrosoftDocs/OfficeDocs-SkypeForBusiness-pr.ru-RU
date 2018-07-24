---
title: Расширитель общих настроек сервера-посредника
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 27a93cb0894f7791b689e4b8fcc3246ab6d9415d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979751"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="a6278-102">Расширитель общих настроек сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a6278-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="a6278-103">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="a6278-103">General settings</span></span>

<span data-ttu-id="a6278-104">Полное доменное имя (FQDN) сервера-посредника пула или сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6278-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="a6278-105">Значение изменяется путем редактирования полного доменного имени сервера.</span><span class="sxs-lookup"><span data-stu-id="a6278-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="a6278-106">Необходима запись узла (A) службы доменных имен (DNS), совпадающая с новым значением.</span><span class="sxs-lookup"><span data-stu-id="a6278-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="a6278-107">В разделе **связи** установите пограничного сервера или пула пограничных серверов для связи с сервером-посредником пула или сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6278-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="a6278-108">Выберите пограничного сервера, сервера-посредника компонентов мультимедиа будет использоваться для внешних пользователей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a6278-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="a6278-109">Если у вас нет пограничного сервера в настоящее время определенные и нужно связать сервер-посредник с пограничного сервера, нажмите кнопку **Создать** и определение нового пограничного сервера или пула пограничных серверов в окне Определение нового пограничного пула мастера.</span><span class="sxs-lookup"><span data-stu-id="a6278-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="a6278-110">Настройки следующего перехода</span><span class="sxs-lookup"><span data-stu-id="a6278-110">Next hop settings</span></span>

<span data-ttu-id="a6278-111">Укажите сервер-посредник пула или сервера-посредника следующего прыжка, выбрав определенного пула переднего плана Enterprise Edition или Standard Edition сервера переднего плана в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="a6278-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="a6278-112">Директор или директора пула не допустимый выбор для пула серверов-посредников или следующего прыжка сервер-посредник и не будет отображаться в списке.</span><span class="sxs-lookup"><span data-stu-id="a6278-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="a6278-113">Нажмите **кнопку ОК** , чтобы принять и сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="a6278-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="a6278-114">Нажмите кнопку **Отмена**, чтобы отменить изменения и покинуть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="a6278-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="a6278-115">Настройки шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="a6278-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="a6278-116">Определите шлюзы ТСОП, связанных с сервером-посредником пула или сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6278-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="a6278-117">Если уже определенного шлюзы, они будут доступны для связи с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="a6278-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="a6278-118">Если разрешено совмещенное расположение сервера-посредника, следует задать диапазон портов прослушивания на серверах пула для протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="a6278-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="a6278-119">По умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="a6278-119">By default, this port is 5067.</span></span> <span data-ttu-id="a6278-120">Если выбран режим **Включить порт TCP**, необходимо задать порт TCP для совмещенного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a6278-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="a6278-121">Это необязательный параметр, который задается в зависимости от требований для шлюза или ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a6278-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="a6278-122">Значение порта TCP по умолчанию: 5068.</span><span class="sxs-lookup"><span data-stu-id="a6278-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="a6278-p105">Магистральные линии связи, которые сопоставлены с сервером-посредником с совмещенным расположением. Если вы уже задали магистральные линии связи, их можно будет сопоставить с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="a6278-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="a6278-125">При наличии более одного магистрали, связанные с сервера-посредника можно указать магистрали по умолчанию, выбрав магистрали выберите команду **Использовать по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="a6278-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="a6278-126">Чтобы отменить выбор шлюза в качестве шлюза по умолчанию, нажмите пункт **Отменить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="a6278-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

