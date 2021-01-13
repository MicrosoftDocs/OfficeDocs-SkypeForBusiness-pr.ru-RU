---
title: Добавление сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Выполните приведенные ниже действия, чтобы добавить новый сервер в существующий пул следующих серверов:'
ms.openlocfilehash: 853ed95ab456bcbbbeffec493effbe86d8894327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811560"
---
# <a name="add-server"></a><span data-ttu-id="22af6-103">Добавление сервера</span><span class="sxs-lookup"><span data-stu-id="22af6-103">Add Server</span></span>
 
<span data-ttu-id="22af6-104">Выполните приведенные ниже действия, чтобы добавить новый сервер в существующий пул следующих серверов:</span><span class="sxs-lookup"><span data-stu-id="22af6-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="22af6-105">интерфейсных серверов Enterprise Edition;</span><span class="sxs-lookup"><span data-stu-id="22af6-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="22af6-106">директоров;</span><span class="sxs-lookup"><span data-stu-id="22af6-106">Director server</span></span>
    
- <span data-ttu-id="22af6-107">серверов-посредников;</span><span class="sxs-lookup"><span data-stu-id="22af6-107">Mediation Server</span></span>
    
- <span data-ttu-id="22af6-108">серверов аудио- и видеоконференций;</span><span class="sxs-lookup"><span data-stu-id="22af6-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="22af6-109">серверов доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="22af6-109">Trusted Application server</span></span>
    
<span data-ttu-id="22af6-p101">Каждый новый сервер пула имеет особые требования. Найдите в следующих разделах тип сервера, добавляемый в существующий пул, и предоставьте запрошенные сведения, определенные для каждого типа серверов. Запрошенные сведения необходимо предоставить для определения нового сервера пула.</span><span class="sxs-lookup"><span data-stu-id="22af6-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="22af6-113">**Интерфейсный сервер Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="22af6-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="22af6-114">Полное доменное имя нового сервера, как оно указано в DNS.</span><span class="sxs-lookup"><span data-stu-id="22af6-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="22af6-p102">Выберите пункт **Использовать все настроенные IP-адреса**, который указывает возможность использования любых IP-адресов, определенных на этом компьютере. Кроме того, можно выбрать пункт **Ограничить использование службы выбранными IP-адресами** и ввести определенный адрес на новом сервере. Указанный IP-адрес является единственным IP-адресом, который будет отвечать на запросы к размещенным службам.</span><span class="sxs-lookup"><span data-stu-id="22af6-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="22af6-118">Определите **IP-адрес ТСОП**, если сервер-посредник совмещен с интерфейсным сервером.</span><span class="sxs-lookup"><span data-stu-id="22af6-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="22af6-119">Выберите пункт **Включить IPv6**, чтобы включить IPv6 на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="22af6-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="22af6-120">**Директор**</span><span class="sxs-lookup"><span data-stu-id="22af6-120">**Director server**</span></span>
  
- <span data-ttu-id="22af6-121">Полное доменное имя нового сервера в соответствии с DNS-сервером.</span><span class="sxs-lookup"><span data-stu-id="22af6-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="22af6-p103">Выберите пункт **Использовать все настроенные IP-адреса**, который указывает возможность использования любых IP-адресов, определенных на этом компьютере. Кроме того, можно выбрать пункт **Ограничить использование службы выбранными IP-адресами** и ввести определенный адрес на новом сервере. Указанный IP-адрес является единственным IP-адресом, который будет отвечать на запросы к размещенным службам.</span><span class="sxs-lookup"><span data-stu-id="22af6-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="22af6-125">**Сервер-посредник**</span><span class="sxs-lookup"><span data-stu-id="22af6-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="22af6-126">Полное доменное имя нового сервера в соответствии с DNS-сервером.</span><span class="sxs-lookup"><span data-stu-id="22af6-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="22af6-p104">Выберите пункт **Использовать все настроенные IP-адреса**, который указывает возможность использования любых IP-адресов, определенных на этом компьютере. Кроме того, можно указать **Ограничить использование службы выбранными IP-адресами** и указать определенный IP-адрес на новом сервере в качестве основного IP-адреса, а также IP-адрес для телефонной сети общего пользования (ТСОП). Указанные IP-адреса являются единственными IP-адресами, которые будут отвечать на запросы к размещенным службам.</span><span class="sxs-lookup"><span data-stu-id="22af6-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22af6-p105">Что касается сервера-посредника, IP-адрес, указанный в качестве основного IP-адреса, и IP-адрес ТСОП по умолчанию являются одним и тем же адресом. IP-адреса могут быть отдельными, если используются выделенные сетевые интерфейсы или на одном сетевом интерфейсе используется несколько адресов. При наличии двух сетевых интерфейсов (один для подключения по локальной сети, а другой — для связи с ТСОП) необходимо назначить разные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="22af6-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="22af6-133">**Сервер аудио- и видеоконференций**</span><span class="sxs-lookup"><span data-stu-id="22af6-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="22af6-134">Полное доменное имя нового сервера в соответствии с DNS-сервером.</span><span class="sxs-lookup"><span data-stu-id="22af6-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="22af6-p106">Выберите пункт **Использовать все настроенные IP-адреса**, который указывает возможность использования любых IP-адресов, определенных на этом компьютере. Кроме того, можно выбрать пункт **Ограничить использование службы выбранными IP-адресами** и ввести определенный адрес на новом сервере. Указанный IP-адрес является единственным IP-адресом, который будет отвечать на запросы к размещенным службам.</span><span class="sxs-lookup"><span data-stu-id="22af6-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="22af6-138">**Сервер доверенных приложений**</span><span class="sxs-lookup"><span data-stu-id="22af6-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="22af6-139">Полное доменное имя нового сервера в соответствии с DNS-сервером.</span><span class="sxs-lookup"><span data-stu-id="22af6-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

