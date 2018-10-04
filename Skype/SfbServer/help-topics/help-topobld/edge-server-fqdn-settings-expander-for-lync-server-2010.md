---
title: Расширитель параметров полного доменного ИМЕНИ пограничного сервера Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: Чтобы определить свойства в области внешние параметры, настройте следующие параметры.
ms.openlocfilehash: d925da792e2c2c296707a99d6a4ae6b29c0545a9
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375610"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="0292f-103">Расширитель параметров полного доменного ИМЕНИ пограничного сервера Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0292f-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="0292f-104">Чтобы определить свойства в области **внешние параметры**, настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0292f-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="0292f-105">Выберите **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** флажок, если нужно определить четкие полное доменное имя пула и IP-адресов для веб-конференций и аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="0292f-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0292f-106">Если вы решаете не устанавливайте флажок для отдельных полное доменное имя и IP-адресов, необходимо задать четкие порты для каждого из трех службы, предоставляемые пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0292f-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="0292f-107">Только полное доменное имя, которое нужно настроить — это полное доменное имя, связанное со службой пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="0292f-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="0292f-108">Выберите **A аудио- и видеоконференций — поддержкой преобразования сетевых адресов** флажок, если вы хотите, чтобы A / V Edge службы для использования в сети адрес преобразования Сетевых адресов IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="0292f-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="0292f-109">Для включенных служб пограничных введите **Полное доменное имя пула** и номер порта в поле **порты**</span><span class="sxs-lookup"><span data-stu-id="0292f-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="0292f-110">Определение полного доменного ИМЕНИ пула **Пограничная служба доступа** и порт, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="0292f-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="0292f-111">Определение полного доменного ИМЕНИ пула **Web конференций** (Если включить отдельное полное доменное имя и IP-адрес для веб-конференций и аудио- и видеоконференций не выбран) и номер порта, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="0292f-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="0292f-112">Определение **A / V Edge службы** полное доменное имя пула (Если включить отдельное полное доменное имя и IP-адрес для веб-конференций и аудио- и видеоконференций не выбран) и номер порта, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="0292f-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="0292f-113">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="0292f-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="0292f-114">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="0292f-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="0292f-115">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="0292f-115">**Help** Displays this help screen.</span></span>
  

