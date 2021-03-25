---
title: Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Узнайте, как установить языки автоматического секретаря аудиоконференции для номера аудиоконференции в Skype для бизнеса Online.
ms.openlocfilehash: d2b4c0d9be666a6ee7de9c2bd36b8dd06cccdf32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110005"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="cfef1-103">Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cfef1-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="cfef1-104">Сведения об установке языков автоматического секретаря в Microsoft Teams см. в статье [Установка языков автоматического секретаря аудиоконференции в группах Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span><span class="sxs-lookup"><span data-stu-id="cfef1-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="cfef1-105">Автоматический секретарь аудиоконференции для Skype для бизнеса может приветствовать звонящих по телефону при их присоединении к собранию на нескольких различных языках.</span><span class="sxs-lookup"><span data-stu-id="cfef1-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="cfef1-106">Выберите один основной язык и до четырех дополнительных языков.</span><span class="sxs-lookup"><span data-stu-id="cfef1-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="cfef1-107">Основной язык, который вы установили, автосекретарь будет использовать первым, а дополнительные языки будут использоваться автосекретарем в выбранном вами порядке.</span><span class="sxs-lookup"><span data-stu-id="cfef1-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="cfef1-108">Изменить можно только языки номеров аудиоконференций, которые имеют категорию "Выделенный".</span><span class="sxs-lookup"><span data-stu-id="cfef1-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="cfef1-109">Языки общего номера аудиоконференции изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="cfef1-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="cfef1-110">Установка языков автоматического секретаря конференции</span><span class="sxs-lookup"><span data-stu-id="cfef1-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="cfef1-111">Для выполнения этого шага [необходимо быть глобальным](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) администратором или администратором [Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cfef1-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="cfef1-112">В Центре **администрирования Skype для бизнеса** на левой навигации перейдите на **устаревший портал.**</span><span class="sxs-lookup"><span data-stu-id="cfef1-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="cfef1-113">На устаревшем портале выберите "Аудиоконференция" и щелкните мост **Microsoft.** </span><span class="sxs-lookup"><span data-stu-id="cfef1-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="cfef1-114">Выберите номер телефона аудиоконференции из списка и в области действий нажмите кнопку "Выбрать **языки".**</span><span class="sxs-lookup"><span data-stu-id="cfef1-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="cfef1-115">Изменить можно только языки выделенных номеров аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="cfef1-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="cfef1-116">На странице **Установка языков** выберите список **Основной язык**, чтобы просмотреть полный список доступных языков.</span><span class="sxs-lookup"><span data-stu-id="cfef1-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="cfef1-117">При необходимости щелкните каждый из списков **Дополнительных языков**, чтобы выбрать дополнительный язык.</span><span class="sxs-lookup"><span data-stu-id="cfef1-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cfef1-118">Перечисляются поддерживаемые основной и дополнительные языки</span><span class="sxs-lookup"><span data-stu-id="cfef1-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="cfef1-119">Порядок их выбора в списках будет порядок языков, которые перечислены вызывателям.</span><span class="sxs-lookup"><span data-stu-id="cfef1-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="cfef1-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cfef1-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="cfef1-121">Что еще мне нужно знать?</span><span class="sxs-lookup"><span data-stu-id="cfef1-121">Want else should I know?</span></span>

- <span data-ttu-id="cfef1-122">Со списком поддерживаемых языков для аудиоконференций можно ознакомиться в статье [Поддерживаемые языки аудиоконференций](/MicrosoftTeams/audio-conferencing-supported-languages).</span><span class="sxs-lookup"><span data-stu-id="cfef1-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="cfef1-123">Языки можно задать для персональных телефонных номеров, телефонных номеров совместного пользования.</span><span class="sxs-lookup"><span data-stu-id="cfef1-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="cfef1-124">Список стран и регионов, в которых доступна аудиоконференция в Microsoft 365 или Office 365 с использованием Майкрософт в качестве поставщика, см. в области номеров телефонов для аудиоконференции. [](phone-numbers-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="cfef1-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="cfef1-125">Хотите использовать Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cfef1-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="cfef1-126">Для автоматизации этого шага можно использовать [cmdlets Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) и [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)</span><span class="sxs-lookup"><span data-stu-id="cfef1-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) and [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlets.</span></span>
  
<span data-ttu-id="cfef1-127">Подробнее см. в Windows PowerShell выполнения распространенных задач управления Skype для бизнеса [Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="cfef1-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cfef1-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cfef1-128">Related topics</span></span>

[<span data-ttu-id="cfef1-129">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="cfef1-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)