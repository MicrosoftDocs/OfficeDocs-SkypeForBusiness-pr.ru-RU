---
title: Расширитель параметров полного доменного имени пограничного сервера для Lync Server 2010
ms.reviewer: ''
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
ms.openlocfilehash: 3ebd98c17f7b32af72809375bd17e55514684e6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882350"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="5da5c-103">Расширитель параметров полного доменного имени пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5da5c-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="5da5c-104">Чтобы определить свойства в области **внешние параметры**, настройте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="5da5c-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="5da5c-105">Выберите **отдельные разрешить полное доменное имя и IP-адреса для веб-конференций и A / V** флажок, если нужно определить четкие полное доменное имя пула и IP-адресов для веб-конференций и аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="5da5c-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5da5c-106">Если вы решаете не устанавливайте флажок для отдельных полное доменное имя и IP-адресов, необходимо задать четкие порты для каждого из трех службы, предоставляемые пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5da5c-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="5da5c-107">Только полное доменное имя, которое нужно настроить — это полное доменное имя, связанное со службой пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="5da5c-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="5da5c-108">Выберите **A аудио- и видеоконференций — поддержкой преобразования сетевых адресов** флажок, если вы хотите, чтобы A / V Edge службы для использования в сети адрес преобразования Сетевых адресов IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="5da5c-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="5da5c-109">Для включенных служб пограничных введите **Полное доменное имя пула** и номер порта в поле **порты**</span><span class="sxs-lookup"><span data-stu-id="5da5c-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="5da5c-110">Определение полного доменного ИМЕНИ пула **Пограничная служба доступа** и порт, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="5da5c-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="5da5c-111">Определение полного доменного ИМЕНИ пула **Web конференций** (Если включить отдельное полное доменное имя и IP-адрес для веб-конференций и аудио- и видеоконференций не выбран) и номер порта, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="5da5c-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="5da5c-112">Определение **A / V Edge службы** полное доменное имя пула (Если включить отдельное полное доменное имя и IP-адрес для веб-конференций и аудио- и видеоконференций не выбран) и номер порта, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="5da5c-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="5da5c-113">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5da5c-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="5da5c-114">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="5da5c-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="5da5c-115">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="5da5c-115">**Help** Displays this help screen.</span></span>
  

