---
title: Запрос сертификата (центр сертификации)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'При создании запроса сертификата, адресованного локальному центру сертификации (обычно это серверы, расположенные во внутренней сети), на странице Выбор центра сертификации (ЦС) предоставляются две возможности:'
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805329"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="e31a1-103">Запрос сертификата (центр сертификации)</span><span class="sxs-lookup"><span data-stu-id="e31a1-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="e31a1-104">При создании запроса сертификата, адресованного локальному центру сертификации (обычно это серверы, расположенные во внутренней сети), на странице **Выбор центра сертификации (ЦС)** предоставляются две возможности:</span><span class="sxs-lookup"><span data-stu-id="e31a1-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="e31a1-105">Выбор центра сертификации из списка ЦС, обнаруженных в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="e31a1-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="e31a1-106">Указание другого центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="e31a1-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="e31a1-107">Если выбрать первый вариант, вы увидите список, содержащий все органы сертификации на основе Windows Server, обнаруженные в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="e31a1-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="e31a1-108">Выберите подходящий центр сертификации для своего сертификата.</span><span class="sxs-lookup"><span data-stu-id="e31a1-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="e31a1-109">При определении нужного ЦС вам может потребоваться консультация администратора ЦС.</span><span class="sxs-lookup"><span data-stu-id="e31a1-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="e31a1-p102">Выбрав второй вариант, введите полное доменное имя и экземпляр ЦС для центра сертификации, который будет использоваться для вашего сертификата. Этот вариант подходит для случая, когда нужный ЦС не является ЦС на основе Windows Server, но будет работать для ЦС на основе Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e31a1-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e31a1-112">Обязательно проверьте участие в группах, необходимое для успешного выполнения запроса сертификации.</span><span class="sxs-lookup"><span data-stu-id="e31a1-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="e31a1-113">Обычно требования к разрешениям для сертификации отличаются от требований к установке Skype для бизнеса Server на серверах.</span><span class="sxs-lookup"><span data-stu-id="e31a1-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="e31a1-114">Узнайте у своего администратора ЦС требования для запроса сертификата.</span><span class="sxs-lookup"><span data-stu-id="e31a1-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

