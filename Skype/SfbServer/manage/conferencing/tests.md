---
title: Проверка конференц-связи с телефонным подключением в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Сводка: Узнайте, как проверить телефонных конференций в Скайп для Business Server 2015.'
ms.openlocfilehash: 7e6e53d5d4ee3e3e28beadc54ca86a79c6118637
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569273"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server-2015"></a><span data-ttu-id="dd6b4-103">Проверка конференц-связи с телефонным подключением в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd6b4-103">Test dial-in conferencing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd6b4-104">**Сводка:** Узнайте, как проверить телефонных конференций в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dd6b4-105">Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="dd6b4-106">Также следует проверить, что веб-страница "Параметры конференц-связи с телефонным подключением" и номера доступа к телефонному подключению работают правильно.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="dd6b4-107">Поиск абонентских групп с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа</span><span class="sxs-lookup"><span data-stu-id="dd6b4-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="dd6b4-108">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dd6b4-109">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dd6b4-110">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-110">Run the following at the command prompt:</span></span>
    
  ```
  Get-CsDialinConferencingAccessNumber -EmptyRegion
  ```

    <span data-ttu-id="dd6b4-111">Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="dd6b4-112">Для получения дополнительных сведений см [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dd6b4-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="dd6b4-113">Поиск номеров доступа, которые не связаны ни с одним регионом</span><span class="sxs-lookup"><span data-stu-id="dd6b4-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="dd6b4-114">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dd6b4-115">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dd6b4-116">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-116">Run the following at the command prompt:</span></span>
    
  ```
  Get-CsDialinConferencingAccessNumber -Region NULL
  ```

    <span data-ttu-id="dd6b4-117">Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="dd6b4-118">Для получения дополнительных сведений см [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dd6b4-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="dd6b4-119">Проверка веб-страницы и номеров доступа</span><span class="sxs-lookup"><span data-stu-id="dd6b4-119">Test webpage and access numbers</span></span>

<span data-ttu-id="dd6b4-120">Чтобы убедиться, что веб-страница «Параметры конференц-связи с телефонным подключением» и номера доступа к телефонному подключению работают правильно, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="dd6b4-121">Протестируйте веб-страницу «Параметры конференц-связи с телефонным подключением», выполнив вход с использованием простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="dd6b4-p102">Протестируйте правильность работы номеров доступа для определенного пула, запустив описанный ниже сценарий. Этот сценарий имитирует звонки на номера доступа. Для его использования вам требуется SIP-адрес и учетные данные одного клиента объединенных коммуникаций, размещенного в этом заданном пуле.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="dd6b4-125">Тестирование номеров доступа для определенного пула</span><span class="sxs-lookup"><span data-stu-id="dd6b4-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="dd6b4-126">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="dd6b4-127">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dd6b4-128">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="dd6b4-128">Run the following at the command prompt:</span></span>
    
  ```
  $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
  ```

    <span data-ttu-id="dd6b4-129">Полученный отчет показывает успешность или сбой операции, а также содержит диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="dd6b4-130">- Verbose флаг содержит более подробные сведения о сколько найдены номера доступа и сведений о них.</span><span class="sxs-lookup"><span data-stu-id="dd6b4-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="dd6b4-131">Для получения дополнительных сведений см [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dd6b4-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

