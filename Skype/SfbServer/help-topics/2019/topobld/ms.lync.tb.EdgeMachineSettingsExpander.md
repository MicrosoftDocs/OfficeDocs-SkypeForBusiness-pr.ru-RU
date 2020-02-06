---
title: Расширитель параметров пограничного компьютера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы изменить свойства сервера в пуле пограничных серверов, выполните указанные ниже действия.
ms.openlocfilehash: 1b2fce33b65e744c8ba2f18107d4f6bc5369b8de
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793807"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="4f1e2-103">Расширитель параметров пограничного компьютера</span><span class="sxs-lookup"><span data-stu-id="4f1e2-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="4f1e2-104">Чтобы изменить свойства сервера в пуле пограничных серверов, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="4f1e2-105">Чтобы изменить полное доменное имя **или полное доменное** имя (FQDN), необходимо отредактировать его.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="4f1e2-106">Полное доменное имя должно соответствовать DNS-записи узла (A) и имени субъекта сертификата, назначенного серверу внутреннему сетевому интерфейсу Edge.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="4f1e2-107">Значение **внутреннего IP-адреса** . определяет IP-адрес, назначенный сетевому интерфейсу, который определен как внутренняя сеть, относительно структуры демилитаризованной сети.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="4f1e2-108">В следующих трех разделах диалогового окна определяются IP-адреса внешней конфигурации этого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="4f1e2-109">Изменение IP-адресов зависит от того, что параметр **включает отдельное полное доменное имя и IP-адрес для Конференции и/V** в параметрах свойств на уровне пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="4f1e2-110">Доступ SIP</span><span class="sxs-lookup"><span data-stu-id="4f1e2-110">SIP Access</span></span>

<span data-ttu-id="4f1e2-111">Измените внешний IP-адрес, назначенный сетевому интерфейсу для доступа к протоколу SIP.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="4f1e2-112">Этот IP-адрес может быть общедоступным IP-адресом или адресом в диапазоне частных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f1e2-113">Если параметр **включить отдельное полное доменное имя и IP-адрес для Конференции и/V** на странице Параметры пула включена, только IP-адрес для доступа к SIP будет доступен для редактирования.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="4f1e2-114">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="4f1e2-114">Web Conferencing</span></span>

<span data-ttu-id="4f1e2-115">Измените внешний IP-адрес, назначенный сетевому интерфейсу для веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="4f1e2-116">Этот IP-адрес может быть общедоступным IP-адресом или адресом в диапазоне частных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="4f1e2-117">Аудио и видео</span><span class="sxs-lookup"><span data-stu-id="4f1e2-117">Audio/Video</span></span>

<span data-ttu-id="4f1e2-118">Измените внешний IP-адрес, назначенный сетевому интерфейсу для звуковых и видеофайлов (A/V).</span><span class="sxs-lookup"><span data-stu-id="4f1e2-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="4f1e2-119">Этот IP-адрес может быть общедоступным IP-адресом или адресом в диапазоне частных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="4f1e2-120">Параметр для **общедоступного IP-адреса, поддерживающего NAT** , — это общедоступный адрес, который используется внешним интерфейсом для сетевого интерфейса A/V или пограничного сервера в целом.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="4f1e2-121">Если параметр **включить отдельное полное доменное имя и IP-адрес для Конференции и/V** включен, этот общедоступный IP-адрес используется для всех трех внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="4f1e2-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

