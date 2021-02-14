---
title: Расширитель параметров полного доменного имени пограничного сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: Чтобы определить свойства в области Внешние параметры, выполните следующую настройку.
ms.openlocfilehash: 6075fab9dbc820b725beec8be4a674a828b4c7d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807099"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6d48b-103">Расширитель параметров полного доменного имени пограничного сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6d48b-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="6d48b-104">Чтобы определить свойства в области **Внешние параметры**, выполните следующую настройку.</span><span class="sxs-lookup"><span data-stu-id="6d48b-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="6d48b-105">Установите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**, чтобы определить отдельное полное доменное имя пула и IP-адреса для видеоконференций и аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="6d48b-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d48b-106">Если флажок для отдельных FQDN и IP-адресов не выбран, необходимо предоставить отдельные порты для каждой из трех служб, предоставляемых edge Server.</span><span class="sxs-lookup"><span data-stu-id="6d48b-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="6d48b-107">Единственное полное доменное имя, которое необходимо настроить, — это полное доменное имя, связанное со службой доступа.</span><span class="sxs-lookup"><span data-stu-id="6d48b-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="6d48b-108">Если служба **A/V Edge** использует IP-адрес и конфигурацию трансляции сетевых адресов (NAT), выберите для нее включенный NAT-адрес.</span><span class="sxs-lookup"><span data-stu-id="6d48b-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="6d48b-109">Для включенных служб пограничных адресов введите **Полное доменное имя пула** и номер порта в поле **Порты**</span><span class="sxs-lookup"><span data-stu-id="6d48b-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="6d48b-110">Укажите полное доменное имя пула для **пограничной службы доступа** и порт, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="6d48b-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="6d48b-111">Укажите полное доменное имя пула для **службы пограничного сервера веб-конференций** (если не установлен флажок "Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций") и порт, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="6d48b-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="6d48b-112">Укажите полное доменное имя пула для **пограничной службы аудио- и видеоконференций** (если не установлен флажок "Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций") и порт, который уникальным образом определяет службу.</span><span class="sxs-lookup"><span data-stu-id="6d48b-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="6d48b-113">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="6d48b-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="6d48b-114">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="6d48b-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="6d48b-115">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="6d48b-115">**Help** Displays this help screen.</span></span>
  

