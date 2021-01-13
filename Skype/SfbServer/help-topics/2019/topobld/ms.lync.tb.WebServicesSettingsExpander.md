---
title: Расширитель параметров веб-служб
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: В построите топологий можно изменить параметры портов, используемые как для внутренних, так и для внешних веб-служб. Кроме того, при развертывании балансировки нагрузки на DNS можно использовать построитель топологий для настройки полного доменного имени пула, разрешаемого в физические IP-адреса всех серверов в этом пуле.
ms.openlocfilehash: 99f052ebbfc4199f077744eee444333822075c24
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800699"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="b40d3-104">Расширитель параметров веб-служб</span><span class="sxs-lookup"><span data-stu-id="b40d3-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="b40d3-105">В построите топологий можно изменить параметры портов, используемые как для внутренних, так и для внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="b40d3-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="b40d3-106">Кроме того, при развертывании балансировки нагрузки на DNS можно использовать построитель топологий для настройки полного доменного имени пула, разрешаемого в физические IP-адреса всех серверов в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="b40d3-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="b40d3-107">Изменение параметров веб-служб</span><span class="sxs-lookup"><span data-stu-id="b40d3-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="b40d3-108">выберите соответствующий сервер переднего плана Standard Edition или пул серверов переднего плана Enterprise Edition, а затем щелкните **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="b40d3-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="b40d3-109">В диалоговом окне **Изменение свойств** выберите вкладку **Веб-службы**.</span><span class="sxs-lookup"><span data-stu-id="b40d3-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b40d3-110">Если имеется несколько пулов переднего сервера или серверов переднего сервера, то внешнее FQDN веб-служб должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="b40d3-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="b40d3-111">Например, если для внешнего веб-службы задавалось FQDN сервера переднего **pool01.contoso.com,** нельзя использовать pool01.contoso.com для другого пула переднего pool01.contoso.com или сервера переднего сервера. </span><span class="sxs-lookup"><span data-stu-id="b40d3-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="b40d3-112">Если также развертываются директоры, то внешнее FQDN веб-служб, определенное для любого директора или пула директоров, должно быть уникальным для любого другого директора или пула директоров, а также любого пула переднего или переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="b40d3-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="b40d3-113">Если вы решите переопредить внутренние веб-службы с помощью самоопределяемого FQDN, каждое FQDN должно быть уникальным из любого другого пула переднего входа, директора или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="b40d3-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="b40d3-114">При изменении свойств пула Enterprise Edition вы можете выбрать параметр **Переопределить полное доменное имя**.</span><span class="sxs-lookup"><span data-stu-id="b40d3-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="b40d3-115">Его следует выбирать только в случае использования балансировки нагрузки службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="b40d3-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="b40d3-116">Если вы используете балансировку нагрузки службы доменных имен (DNS), выберите **Переопределить полное доменное имя** и введите в текстовом поле полное доменное имя пула, разрешающееся в физические IP-адреса всех серверов в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="b40d3-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="b40d3-117">Если вы не используете балансировку нагрузки службы доменных имен (DNS) и не выбираете параметр **Переопределить полное доменное имя**, то изменить полное доменное имя внутренних веб-служб нельзя.</span><span class="sxs-lookup"><span data-stu-id="b40d3-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="b40d3-118">FQDN внутренних веб-служб это URL-адрес, используемый внутренними пользователями для подключения к Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b40d3-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="b40d3-p105">При необходимости введите новые значения HTTP, HTTPS или HTTP и HTTPS для **Порты прослушивания** и **Опубликованные порты**. Порты прослушивания используются службами IIS для ожидания передачи входящего трафика SIP; опубликованные порты настроены в подсистеме балансировки нагрузки или на обратном прокси-севере и также используются для ожидания передачи входящего трафика SIP. По умолчанию как порт прослушивания HTTP, так и опубликованный  порт HTTP имеют номер 80; оба соответствующих HTTPS-портов имеют номер 443. Значением по умолчанию для двух опубликованных портов HTTP является 8080, а для соответствующих HTTPS-портов — 4443.</span><span class="sxs-lookup"><span data-stu-id="b40d3-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="b40d3-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b40d3-123">Click **OK**.</span></span>
    
<span data-ttu-id="b40d3-124">Если вы изменяете внутреннее полное доменное имя или назначения любых портов прослушивания, следует повторить локальную установку на всех серверах в пуле, чтобы эти изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="b40d3-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

