---
title: Настройка магазина личных контактов на клиентских компьютерах Lync 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: Сводка. Настройте личный магазин контактов, используемый устаревшими клиентами.
ms.openlocfilehash: 5f2131fd1e960e658d4257f0c86dd61a241aa499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109675"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="a33d8-103">Настройка магазина личных контактов на клиентских компьютерах Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a33d8-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="a33d8-104">Если вы интегрировали Skype для бизнеса Server 2015 и Exchange Server 2016 или Exchange Server 2013 г., необходимо настроить личный магазин контактов, используемый клиентами.</span><span class="sxs-lookup"><span data-stu-id="a33d8-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="a33d8-105">В частности, необходимо настроить Skype для бизнеса, чтобы использовать Exchange в качестве личного магазина контактов, и в то же время убедиться, что пользователи не могут переопределять это решение.</span><span class="sxs-lookup"><span data-stu-id="a33d8-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="a33d8-106">Это можно сделать, создав и настроив значение Реестра на каждом клиентский компьютер.</span><span class="sxs-lookup"><span data-stu-id="a33d8-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a33d8-107">Следующая процедура необходима только для клиентов, использующих клиента Lync 2010 или ранее.</span><span class="sxs-lookup"><span data-stu-id="a33d8-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="a33d8-108">Клиент Lync 2013 и все клиенты Skype для бизнеса не смогут переопределять параметры магазина контактов.</span><span class="sxs-lookup"><span data-stu-id="a33d8-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="a33d8-109">Чтобы настроить данное значение на одном компьютере, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a33d8-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="a33d8-110">На клиентский компьютер нажмите **кнопку Начните и** нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a33d8-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="a33d8-111">В диалоговом окне **Выполнить** введите regedit, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="a33d8-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="a33d8-112">В редакторе реестра расширим HKEY_LOCAL_MACHINE, расширим программное **обеспечение,** расширим **политики,** расширим **Microsoft,** а затем **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="a33d8-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="a33d8-113">Щелкните **правой кнопкой мыши Communicator,** указать **значение New**, а затем нажмите **значение DWORD (32-bit).**</span><span class="sxs-lookup"><span data-stu-id="a33d8-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="a33d8-114">После создания значения введите PersonalContactStoreOverride и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="a33d8-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="a33d8-115">Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.</span><span class="sxs-lookup"><span data-stu-id="a33d8-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="a33d8-116">Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="a33d8-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="a33d8-117">Дополнительные сведения об этом в Windows 10 см. в статье [Create a Group Policy Object.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="a33d8-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
