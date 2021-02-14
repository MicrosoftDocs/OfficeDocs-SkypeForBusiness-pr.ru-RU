---
title: Расширитель параметров пограничного компьютера
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
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: Чтобы изменить свойства сервера в пуле пограничных серверов, выполните следующие действия.
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807129"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="fa40c-103">Расширитель параметров пограничного компьютера</span><span class="sxs-lookup"><span data-stu-id="fa40c-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="fa40c-104">Чтобы изменить свойства сервера в пуле пограничных серверов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa40c-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="fa40c-p101">**Внутреннее имя или полное доменное имя** могут быть изменены путем редактирования полного доменного имени. Полное доменное имя должно соответствовать DNS-записи узла (А) и имени субъекта сертификата, назначенного внутреннему сетевому интерфейсу на этом пограничном сервере. Значение **Внутренний IP-адрес** определяет IP-адрес, назначенный сетевому интерфейсу внутренней сети (относительно заданной сети периметра).</span><span class="sxs-lookup"><span data-stu-id="fa40c-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="fa40c-p102">В следующих трех разделах данного диалогового окна определяются IP-адреса внешней конфигурации данного пограничного сервера. Возможность менять IP-адреса зависит от параметра **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**, который задается в параметрах "Свойства" на уровне пула пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="fa40c-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="fa40c-110">Доступ SIP</span><span class="sxs-lookup"><span data-stu-id="fa40c-110">SIP Access</span></span>

<span data-ttu-id="fa40c-p103">Измените внешний IP-адрес, назначенный сетевому интерфейсу для доступа SIP. Данный IP-адрес может являться общим IP-адресом или адресом из частного диапазона IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="fa40c-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa40c-113">Если включен параметр **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций** на странице параметров пула, для редактирования будет доступен только IP-адрес, используемый для доступа SIP.</span><span class="sxs-lookup"><span data-stu-id="fa40c-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="fa40c-114">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="fa40c-114">Web Conferencing</span></span>

<span data-ttu-id="fa40c-p104">Измените внешний IP-адрес, назначенный сетевому интерфейсу для веб-конференций. Данный IP-адрес может являться общим IP-адресом или адресом из частного диапазона IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="fa40c-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="fa40c-117">"Audio/Video" (Аудио и видео);</span><span class="sxs-lookup"><span data-stu-id="fa40c-117">Audio/Video</span></span>

<span data-ttu-id="fa40c-p105">Измените внешний IP-адрес, назначенный сетевому интерфейсу для звука и видео. Данный IP-адрес может являться общим IP-адресом или адресом из частного диапазона IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="fa40c-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="fa40c-p106">Значением параметра **Используемый общий IP-адрес с поддержкой NAT** является общедоступный адрес, используемый внешним интерфейсом для сетевого интерфейса звука и видео или пограничного сервера в целом. Если параметр **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций** включен, этот IP-адрес используется для всех трех внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="fa40c-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

