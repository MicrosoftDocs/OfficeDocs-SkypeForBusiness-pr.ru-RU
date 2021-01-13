---
title: Сопоставление сервера переднего плана с AV MCU
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
ROBOTS: NOINDEX, NOFOLLOW
description: Аудио- и видеоконференции позволяют пользователям использовать аудио- и видеосвязь в режиме реального времени (пользователи должны иметь соответствующие клиентские устройства, такие как гарнитуры для аудиоконференций и веб-камеры для видеоконференций). Если в развертывании поддерживаются конференции и включены как веб-конференции, так и аудио- и видеоконференции, можно совместить сервер аудио- и видеоконференций и интерфейсный сервер или развернуть один или несколько отдельных серверов аудио- и видеоконференций (пул аудио- и видеоконференций). При выборе варианта развертывания отдельного сервера A/V Conferencing Server необходимо определить его в построитель топологий.
ms.openlocfilehash: 24aec4c97b1d9a0f30ef8e775d04b93d7de4fec2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811429"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="e2a3b-105">Связывание сервера переднего плана с AV MCU</span><span class="sxs-lookup"><span data-stu-id="e2a3b-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="e2a3b-106">Аудио- и видеоконференции позволяют пользователям использовать аудио- и видеосвязь в режиме реального времени (пользователи должны иметь соответствующие клиентские устройства, такие как гарнитуры для аудиоконференций и веб-камеры для видеоконференций).</span><span class="sxs-lookup"><span data-stu-id="e2a3b-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="e2a3b-107">Если в развертывании поддерживаются конференции и включены как веб-конференции, так и аудио- и видеоконференции, можно совместить сервер аудио- и видеоконференций и интерфейсный сервер или развернуть один или несколько отдельных серверов аудио- и видеоконференций (пул аудио- и видеоконференций).</span><span class="sxs-lookup"><span data-stu-id="e2a3b-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="e2a3b-108">При выборе варианта развертывания отдельного сервера A/V Conferencing Server необходимо определить его в построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="e2a3b-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="e2a3b-109">Все пулы на сайте и пулы нескольких центральных сайтов могут использовать один и тот же сервер A/V Conferencing Server, если использование не превышает емкость сервера A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="e2a3b-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

