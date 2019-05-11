---
title: Настройка хранилища личных контактов на клиентских компьютерах Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Сводка: Настройка личных хранилище контактов, используемого клиентами прежних версий.'
ms.openlocfilehash: 5545f3c0f993b1974f59e90c0b6672f3ebd246e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894262"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="3e953-103">Настройка хранилища личных контактов на клиентских компьютерах Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3e953-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="3e953-104">Если вы реализуете интеграцию Скайп Business Server 2015, Exchange Server 2016 или Exchange Server 2013, следует настроить хранилище личных контактов, используемого клиентами.</span><span class="sxs-lookup"><span data-stu-id="3e953-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="3e953-105">В частности необходимо настроить Скайп для использования Exchange в качестве хранилища личных контактов и, в то же время, убедитесь, что пользователи не могут переопределить это решение.</span><span class="sxs-lookup"><span data-stu-id="3e953-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="3e953-106">Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="3e953-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e953-107">Следующая процедура используется только для клиентов с помощью клиента Lync 2010 или более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="3e953-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="3e953-108">Клиент Lync 2013 и все Скайп пользователей не будут иметь возможность переопределение параметров хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="3e953-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="3e953-109">Чтобы настроить данное значение на одном компьютере, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3e953-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="3e953-110">На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3e953-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="3e953-111">В диалоговом окне **Выполнить** введите regedit, а затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3e953-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="3e953-112">В редакторе реестра последовательно разверните узлы **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft** и **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="3e953-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="3e953-113">Щелкните элемент **Communicator** правой кнопкой мыши, наведите указатель на пункт **Создать** и выберите пункт **Параметр DWORD (32-разрядный)**.</span><span class="sxs-lookup"><span data-stu-id="3e953-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="3e953-114">После создания параметра введите PersonalContactStoreOverride и нажмите клавишу ВВОД, чтобы переименовать параметр.</span><span class="sxs-lookup"><span data-stu-id="3e953-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="3e953-115">Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.</span><span class="sxs-lookup"><span data-stu-id="3e953-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="3e953-116">Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="3e953-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="3e953-117">Для получения дополнительных сведений на это Windows 10 в статье [Создание объекта групповой политики](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .</span><span class="sxs-lookup"><span data-stu-id="3e953-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
