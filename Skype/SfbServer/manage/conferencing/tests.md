---
title: Тестирование телефонных конференций в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Сводка: Узнайте, как проверить телефонных конференций в Скайп для Business Server.'
ms.openlocfilehash: 410cbaa9319130dcf4a98c23360362211869e52f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924887"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="00d14-103">Тестирование телефонных конференций в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="00d14-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="00d14-104">**Сводка:** Узнайте, как проверить телефонных конференций в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d14-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="00d14-105">Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="00d14-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="00d14-106">Также следует проверить, что веб-страница "Параметры конференц-связи с телефонным подключением" и номера доступа к телефонному подключению работают правильно.</span><span class="sxs-lookup"><span data-stu-id="00d14-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="00d14-107">Поиск абонентских групп с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа</span><span class="sxs-lookup"><span data-stu-id="00d14-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="00d14-108">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="00d14-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="00d14-109">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="00d14-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="00d14-110">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="00d14-110">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="00d14-111">Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.</span><span class="sxs-lookup"><span data-stu-id="00d14-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="00d14-112">Для получения дополнительных сведений см [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d14-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="00d14-113">Поиск номеров доступа, которые не связаны ни с одним регионом</span><span class="sxs-lookup"><span data-stu-id="00d14-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="00d14-114">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="00d14-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="00d14-115">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="00d14-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="00d14-116">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="00d14-116">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="00d14-117">Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.</span><span class="sxs-lookup"><span data-stu-id="00d14-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="00d14-118">Для получения дополнительных сведений см [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d14-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="00d14-119">Проверка веб-страницы и номеров доступа</span><span class="sxs-lookup"><span data-stu-id="00d14-119">Test webpage and access numbers</span></span>

<span data-ttu-id="00d14-120">Чтобы убедиться, что веб-страница «Параметры конференц-связи с телефонным подключением» и номера доступа к телефонному подключению работают правильно, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="00d14-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="00d14-121">Протестируйте веб-страницу «Параметры конференц-связи с телефонным подключением», выполнив вход с использованием простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="00d14-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="00d14-p102">Протестируйте правильность работы номеров доступа для определенного пула, запустив описанный ниже сценарий. Этот сценарий имитирует звонки на номера доступа. Для его использования вам требуется SIP-адрес и учетные данные одного клиента объединенных коммуникаций, размещенного в этом заданном пуле.</span><span class="sxs-lookup"><span data-stu-id="00d14-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="00d14-125">Тестирование номеров доступа для определенного пула</span><span class="sxs-lookup"><span data-stu-id="00d14-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="00d14-126">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="00d14-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="00d14-127">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="00d14-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="00d14-128">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="00d14-128">Run the following at the command prompt:</span></span>
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="00d14-129">Полученный отчет показывает успешность или сбой операции, а также содержит диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="00d14-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="00d14-130">- Verbose флаг содержит более подробные сведения о сколько найдены номера доступа и сведений о них.</span><span class="sxs-lookup"><span data-stu-id="00d14-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="00d14-131">Для получения дополнительных сведений см [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d14-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

