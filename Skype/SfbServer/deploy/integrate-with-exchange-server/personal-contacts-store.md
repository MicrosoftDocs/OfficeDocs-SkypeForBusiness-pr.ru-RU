---
title: Настройка хранилища личных контактов на клиентских компьютерах для Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Сводка: Настройка личных хранилище контактов, используемых Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a><span data-ttu-id="688ba-103">Настройка хранилища личных контактов на клиентских компьютерах для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="688ba-103">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="688ba-104">**Сводка:** Настройка хранилища личных контактов, используемых Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="688ba-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="688ba-105">Если вы реализуете интеграцию Скайп Business Server 2015, Exchange Server 2016 или Exchange Server 2013, следует настроить хранилище личных контактов на все клиентские компьютеры под управлением Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="688ba-105">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="688ba-106">В частности необходимо настроить Скайп для использования Exchange в качестве хранилища личных контактов и, в то же время, убедитесь, что пользователи не могут переопределить это решение.</span><span class="sxs-lookup"><span data-stu-id="688ba-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="688ba-107">Это можно сделать, создав и настроив значение реестра на каждом клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="688ba-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="688ba-108">Обратите внимание на то, что это не требуется на компьютерах под управлением Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="688ba-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="688ba-109">Чтобы настроить данное значение на одном компьютере, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="688ba-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="688ba-110">На клиентском компьютере нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="688ba-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="688ba-111">В диалоговом окне **Выполнить** введите regedit, а затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="688ba-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="688ba-112">В редакторе реестра последовательно разверните узлы **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft** и **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="688ba-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="688ba-113">Щелкните элемент **Communicator** правой кнопкой мыши, наведите указатель на пункт **Создать** и выберите пункт **Параметр DWORD (32-разрядный)**.</span><span class="sxs-lookup"><span data-stu-id="688ba-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="688ba-114">После создания нового значения введите PersonalContactStoreOverride и нажмите клавишу ВВОД, чтобы переименовать значение.</span><span class="sxs-lookup"><span data-stu-id="688ba-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="688ba-115">Убедитесь, что значение PersonalContactStoreOverride равно 0, а затем закройте редактор реестра.</span><span class="sxs-lookup"><span data-stu-id="688ba-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="688ba-116">Если нужно внести это изменение на нескольких компьютерах, это можно сделать, создав пользовательский объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="688ba-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="688ba-117">Для получения дополнительных сведений, обратитесь к документации групповой политики на [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span><span class="sxs-lookup"><span data-stu-id="688ba-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

