---
title: Расширитель параметров пограничного сервера
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: Чтобы изменить свойства сервера в пуле пограничных серверов, выполните следующие действия.
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="4f2f0-103">Расширитель параметров пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4f2f0-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="4f2f0-104">Чтобы изменить свойства сервера в пуле пограничных серверов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="4f2f0-105">**Внутреннее имя или полное доменное имя** можно изменить путем редактирования полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="4f2f0-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="4f2f0-106">Полное доменное имя должно соответствовать доменных имен (DNS) узла (A) записи и имя субъекта сертификата, присвоенные серверу для внутреннего интерфейса пограничной сети.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="4f2f0-107">Значение **внутреннего IP-адрес** определяет IP-адрес, назначенный сетевой интерфейс, который определен как внутренней сети, относящиеся к проект демилитаризованной сети.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="4f2f0-108">В следующих трех разделах диалогового окна определяется IP-адресов для внешней конфигурации этот пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="4f2f0-109">Возможность изменения IP-адресов, зависит от параметра **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** на странице свойств параметры на пограничном сервере уровне пула.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="4f2f0-110">Доступ SIP</span><span class="sxs-lookup"><span data-stu-id="4f2f0-110">SIP Access</span></span>

<span data-ttu-id="4f2f0-111">Измените внешний IP-адрес, назначенный сетевой интерфейс для доступа к Session Initiation Protocol (SIP).</span><span class="sxs-lookup"><span data-stu-id="4f2f0-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="4f2f0-112">Данный IP-адрес может быть общедоступный IP-адрес или адрес в частной диапазон IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f2f0-113">Если параметр **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** в пуле "Параметры" Этот параметр включен, IP-адрес для доступа к SIP, будут доступны для редактирования только.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="4f2f0-114">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="4f2f0-114">Web Conferencing</span></span>

<span data-ttu-id="4f2f0-115">Измените внешний IP-адрес, назначенный сетевой интерфейс веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="4f2f0-116">Данный IP-адрес может быть общедоступный IP-адрес или адрес в частной диапазон IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="4f2f0-117">Аудио и видео</span><span class="sxs-lookup"><span data-stu-id="4f2f0-117">Audio/Video</span></span>

<span data-ttu-id="4f2f0-118">Изменить внешний IP-адрес, назначенный сетевой интерфейс для аудио и видео (A / V).</span><span class="sxs-lookup"><span data-stu-id="4f2f0-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="4f2f0-119">Данный IP-адрес может быть общедоступный IP-адрес или адрес в частной диапазон IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="4f2f0-120">Значение параметра **включена функция используется общедоступный IP-адрес** является общей адрес, используемый внешний интерфейс для A / V сетевого интерфейса или пограничного сервера в целом.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="4f2f0-121">Если параметр **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** — этот параметр включен, в этом общедоступный IP-адрес используется для всех трех внешних интерфейсах.</span><span class="sxs-lookup"><span data-stu-id="4f2f0-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

