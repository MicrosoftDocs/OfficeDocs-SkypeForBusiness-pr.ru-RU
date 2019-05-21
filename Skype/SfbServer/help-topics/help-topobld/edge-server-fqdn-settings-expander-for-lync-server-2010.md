---
title: Расширитель параметров полного доменного имени пограничного сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: Чтобы определить свойства в разделе внешние параметры, выполните указанные ниже действия.
ms.openlocfilehash: 6b833e89a8e1288af9a203dd5f44201c253ff2f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282601"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="cdeb5-103">Расширитель параметров полного доменного имени пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cdeb5-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="cdeb5-104">Чтобы определить свойства в разделе **внешние параметры**, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="cdeb5-105">Установите флажок **включить отдельное полное доменное имя и IP-адрес для конференций и/V** , если вы хотите задать индивидуальные доменные имена и IP-адреса для разных пулов и звуковых и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdeb5-106">Если вы решили не установить флажок для отдельных полных доменных имен и IP-адресов, необходимо предоставить отдельные порты для каждой из трех служб, предоставляемых пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="cdeb5-107">Единственным полным доменным именем, которое нужно настроить, является полное доменное имя, связанное со службой Edge Access.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="cdeb5-108">Установите флажок **Служба пограничного устройства NAT включена** , если вы хотите, чтобы служба EDGE (a/v) ИСПОЛЬЗОВАЛА IP-адрес и конфигурацию преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="cdeb5-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="cdeb5-109">Для включенных служб Edge вы вводите **полное доменное имя пула** и порт в разделе Ports ( **порты** ).</span><span class="sxs-lookup"><span data-stu-id="cdeb5-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="cdeb5-110">Определите полное доменное имя пула **службы Edge Access** и порт, который однозначно определяет службу.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="cdeb5-111">Определите полное доменное имя пула **служб для веб-конференций** (если не выбрано отдельное полное доменное имя и IP-адрес) и порт, который однозначно определяет службу.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="cdeb5-112">Определите полное доменное имя пула **служб EDGE (a/v** ) (если включено отдельное полное доменное имя и IP-адрес, а не выбрано значение A/V) и порт, который однозначно определяет службу.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="cdeb5-113">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="cdeb5-114">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="cdeb5-115">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="cdeb5-115">**Help** Displays this help screen.</span></span>
  

