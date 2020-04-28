---
title: Настройка корпоративной голосовой связи с помощью мастера начальной настройки
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a22c741898b48c3d71970699f09c00bb638205f
ms.sourcegitcommit: 3ef5c913318fdeeaa8c55caab07c2f8224eae2b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43898134"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a><span data-ttu-id="5ca89-102">Настройка корпоративной голосовой связи с помощью мастера начальной настройки</span><span class="sxs-lookup"><span data-stu-id="5ca89-102">Use the Getting Started wizard to set up Business Voice</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ca89-103">Информация в этой статье применима только к Business Voice **с** тарифным планом.</span><span class="sxs-lookup"><span data-stu-id="5ca89-103">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="5ca89-104">Корпоративная голосовая связь с тарифным планом доступна только в некоторых странах и регионах.</span><span class="sxs-lookup"><span data-stu-id="5ca89-104">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="5ca89-105">Перед прочтением этой статьи ознакомьтесь со статьей [Страны и регионы, в которых доступна корпоративная голосовая связь](country-region-availability.md), чтобы узнать, поддерживается ли в вашей стране или регионе корпоративная голосовая связь с тарифным планом.</span><span class="sxs-lookup"><span data-stu-id="5ca89-105">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="5ca89-106">Если ваш клиент находится в стране или регионе, не поддерживающем корпоративную голосовую связь с тарифным планом, ознакомьтесь со статьей [Получение справки от торгового представителя или партнера Майкрософт](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="5ca89-106">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="5ca89-107">Мастер начальной настройки корпоративной голосовой связи Microsoft 365 поможет быстро настроить систему, чтобы совершать и принимать телефонные звонки в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5ca89-107">The Getting Started wizard for Microsoft 365 Business Voice gets you set up quickly to make and receive phone calls in Microsoft Teams.</span></span> <span data-ttu-id="5ca89-108">Небольшой начинающей компании мастер поможет быстро начать работу с номерами телефонов, меню звонков, приветствиями и т. д.</span><span class="sxs-lookup"><span data-stu-id="5ca89-108">If you're a small business just starting out, the wizard can get you up and running in a few minutes with phone numbers, call menus, greetings, and more.</span></span> <span data-ttu-id="5ca89-109">В крупных компаниях с существующими решениями телефонной связи этот мастер поможет настроить пилотное решение корпоративной голосовой связи, чтобы несколько пользователей опробовали это решение до его развертывания для всех сотрудников.</span><span class="sxs-lookup"><span data-stu-id="5ca89-109">If you're a larger business with an established telephony solution, the wizard can help you set up a pilot so a few users can try Business Voice before you roll it out for everyone.</span></span> <span data-ttu-id="5ca89-110">В любом случае вы можете начать использовать корпоративную голосовую связь сразу после завершения работы мастера!</span><span class="sxs-lookup"><span data-stu-id="5ca89-110">Either way, you can start using Business Voice as soon as the wizard is finished!</span></span>

<span data-ttu-id="5ca89-111">Перед запуском мастера рекомендуется ознакомиться с этой статьей.</span><span class="sxs-lookup"><span data-stu-id="5ca89-111">It's a good idea to read this article before you start the wizard.</span></span> <span data-ttu-id="5ca89-112">Когда вы будете готовы запустить мастер, выберите **Начать работу** на странице [Начало работы с корпоративной голосовой связью Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice).</span><span class="sxs-lookup"><span data-stu-id="5ca89-112">When you're ready to run the wizard, select **Get started** on the [Get started with Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice) page.</span></span> <span data-ttu-id="5ca89-113">Войдите в систему, используя учетную запись, с помощью которой была создана подписка, или другую учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="5ca89-113">Sign in by using the account you used to create your subscription or another account that's a Global Administrator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ca89-114">Microsoft Teams и корпоративная голосовая связь работает, только если почтовые ящики пользователей находятся в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ca89-114">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="5ca89-115">Почтовые ящики, размещенные на локальном сервере Exchange Server, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5ca89-115">They don't support mailboxes on on-premises Exchange Server.</span></span>

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

<span data-ttu-id="5ca89-116">Если ничего не нужно настраивать прямо сейчас, то на этом готово.</span><span class="sxs-lookup"><span data-stu-id="5ca89-116">If you don't want to customize anything immediately, you're done!</span></span> <span data-ttu-id="5ca89-117">Можно приступить к использованию корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5ca89-117">You can start using Business Voice right away.</span></span>

## <a name="emergency-services-location"></a><span data-ttu-id="5ca89-118">Расположение экстренных служб</span><span class="sxs-lookup"><span data-stu-id="5ca89-118">Emergency services location</span></span>

<table>
    <tr>
        <td><span data-ttu-id="5ca89-119">Если нужно изменить адрес экстренных служб, щелкните <b>Изменить</b> и введите новый адрес.</span><span class="sxs-lookup"><span data-stu-id="5ca89-119">If you want to change the emergency address, click <b>Edit</b>, and then enter a new address.</span></span> <span data-ttu-id="5ca89-120">Введенный адрес будет проверен, чтобы убедиться в его правильности для вызова экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="5ca89-120">The address that you provide is validated to make sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="5ca89-121">Затем этот адрес будет назначен всем пользователям, которым вы назначаете номер на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="5ca89-121">This address is then assigned to all users that you assign a number to in the next step.</span></span> <span data-ttu-id="5ca89-122">Если у вас есть сотрудники в нескольких расположениях, см. <a href="./customize-business-voice.md">Настройка корпоративной голосовой связи</a> для получения сведений о добавлении и назначении дополнительных адресов экстренных служб после завершения работы мастера начальной настройки.</span><span class="sxs-lookup"><span data-stu-id="5ca89-122">If you have employees in more than one location, see <a href="./customize-business-voice.md">Business Voice design customization</a> to add and assign more emergency addresses after you prepare the Getting Started wizard.</span></span></td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

<span data-ttu-id="5ca89-123">Дополнительные сведения см. в статье [Что такое расположения для экстренного реагирования, адреса экстренных служб и маршрутизация экстренных вызовов?](../what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="5ca89-123">For more information, see [What are emergency locations, addresses, and call routing](../what-are-emergency-locations-addresses-and-call-routing.md)?</span></span>

## <a name="company-phone-number"></a><span data-ttu-id="5ca89-124">Номер телефона компании</span><span class="sxs-lookup"><span data-stu-id="5ca89-124">Company phone number</span></span>

<table>
    <tr>
        <td><span data-ttu-id="5ca89-125">Помимо нового местного телефонного номера можно приобрести номер для бесплатных звонков абонентов или перенести существующий номер в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ca89-125">In addition to a new local phone number, you can purchase a toll-free number or port an existing number to Microsoft 365.</span></span> <span data-ttu-id="5ca89-126">Чтобы настроить номер для бесплатных звонков, необходимо приобрести кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="5ca89-126">To set up a toll-free number, you need to purchase Communications Credits.</span></span> <span data-ttu-id="5ca89-127">Чтобы перенести один или несколько номеров в Microsoft 365, перейдите в <a href="https://admin.teams.microsoft.com">Центр администрирования Teams</a> после завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="5ca89-127">To port one or more numbers to Microsoft 365, go to the <a href="https://admin.teams.microsoft.com">Teams admin center</a> after the wizard finishes.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="5ca89-128">Если перенести существующий телефонный номер в Microsoft 365, в мастере по-прежнему будет отображаться временный номер.</span><span class="sxs-lookup"><span data-stu-id="5ca89-128">If you port an existing phone number to Microsoft 365, you'll still see a temporary phone number in the wizard.</span></span> <span data-ttu-id="5ca89-129">Так и должно быть.</span><span class="sxs-lookup"><span data-stu-id="5ca89-129">This is expected.</span></span> <span data-ttu-id="5ca89-130">После завершения работы мастера и процесса переноса временный телефонный номер будет заменен на ваш существующий номер.</span><span class="sxs-lookup"><span data-stu-id="5ca89-130">After you complete the wizard and the porting process, the temporary phone number will be replaced by the pre-existing number.</span></span>

## <a name="user-licenses"></a><span data-ttu-id="5ca89-131">Пользовательские лицензии</span><span class="sxs-lookup"><span data-stu-id="5ca89-131">User licenses</span></span>

<table>
    <tr>
        <td><span data-ttu-id="5ca89-132">Чтобы назначить пользовательские лицензии, выберите сотрудников организации, которым нужно совершать или принимать телефонные звонки вне Teams (например, звонить поставщикам).</span><span class="sxs-lookup"><span data-stu-id="5ca89-132">To assign user licenses, select the people in your organization who need to make or receive phone calls outside of Teams (such as calling a supplier).</span></span> <span data-ttu-id="5ca89-133">Количество назначаемых лицензий корпоративной голосовой связи не должно превышать доступное количество.</span><span class="sxs-lookup"><span data-stu-id="5ca89-133">You can only assign as many Business Voices licenses as you have available.</span></span> <span data-ttu-id="5ca89-134">Если нужно больше лицензий, можно приобрести дополнительные лицензии после завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="5ca89-134">If you need more, you can buy additional licenses after the wizard is finished.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="5ca89-135">После завершения работы мастера можно перенести существующие номера телефонов в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ca89-135">You can port existing phone numbers to Microsoft 365 after the wizard is finished.</span></span> <span data-ttu-id="5ca89-136">После завершения этого процесса перенесенные телефонные номера заменят временные номера, которые были предоставлены мастером.</span><span class="sxs-lookup"><span data-stu-id="5ca89-136">After you complete the porting process, the ported phone numbers will replace the temporary phone numbers that the wizard provided.</span></span>

## <a name="incoming-call-greeting"></a><span data-ttu-id="5ca89-137">Приветствие для входящих звонков</span><span class="sxs-lookup"><span data-stu-id="5ca89-137">Incoming-call greeting</span></span>

<table>
    <tr>
        <td><span data-ttu-id="5ca89-138">Можно отправить аудиофайл (MP3 или WAV) размером до 5 МБ, чтобы использовать его в качестве приветствия. Также можно ввести текст собственного приветствия, а система преобразования текста в речь в Microsoft 365 будет читать этот текст звонящим абонентам.</span><span class="sxs-lookup"><span data-stu-id="5ca89-138">You can upload a sound file (MP3 or WAV) of up to 5 Megabytes (MB) to use as a call greeting, or you can type your greeting, and Microsoft 365 will use text-to-speech to read it to the caller.</span></span> <span data-ttu-id="5ca89-139">Приветствие — то, что абоненты, позвонившие по номеру вашей компании, услышат в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="5ca89-139">The greeting will be the first thing callers hear when they call your company phone number.</span></span> <span data-ttu-id="5ca89-140">Для правильного звучания при использовании преобразования текста в речь может потребоваться использовать фонетическое написание.</span><span class="sxs-lookup"><span data-stu-id="5ca89-140">For text-to-speech, you might need to use phonetic spellings to get the pronunciations correct.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a><span data-ttu-id="5ca89-141">Голосовое меню и перенаправление</span><span class="sxs-lookup"><span data-stu-id="5ca89-141">Call menu and forwarding</span></span>

<table>
    <tr>
        <td><span data-ttu-id="5ca89-142">Можно перенаправлять все звонки определенному пользователю или настроить голосовое меню, в котором абонент сможет выбрать нужный вариант.</span><span class="sxs-lookup"><span data-stu-id="5ca89-142">You can forward all calls to a specific user, or you can set up a menu that the caller can choose options from.</span></span> <span data-ttu-id="5ca89-143">При создании голосового меню можно указать доступные для выбора варианты. Для выбора звонящий абонент должен нажать цифровую кнопку на клавиатуре телефона или произнести голосовую команду.</span><span class="sxs-lookup"><span data-stu-id="5ca89-143">If you create a call menu, you specify options that the caller can select by voice or by pressing a number on a phone's keypad.</span></span> <span data-ttu-id="5ca89-144">При выборе каждого из вариантов в меню можно перенаправлять звонки определенному пользователю.</span><span class="sxs-lookup"><span data-stu-id="5ca89-144">Each menu option can forward calls to a specific user.</span></span><br><br>
        <span data-ttu-id="5ca89-145">Можно отправить аудиофайл (MP3 или WAV) размером до 5 МБ с инструкциями для звонящих абонентов или ввести текст инструкций.</span><span class="sxs-lookup"><span data-stu-id="5ca89-145">You can upload a sound file (MP3 or WAV) of up to 5 MB that gives instructions to the caller, or you can type the instructions.</span></span> <span data-ttu-id="5ca89-146">Система преобразования текста в речь в Microsoft 365 будет читать этот текст звонящим абонентам.</span><span class="sxs-lookup"><span data-stu-id="5ca89-146">Microsoft 365 will use text-to-speech to read them to the caller.</span></span> <span data-ttu-id="5ca89-147">Вам может потребоваться написать слова фонетически, чтобы обеспечить правильное произношение.</span><span class="sxs-lookup"><span data-stu-id="5ca89-147">You might need to spell words phonetically to get the pronunciations right.</span></span>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> <span data-ttu-id="5ca89-148">Мастер «Начало работы» поможет настроить простое меню звонков, чтобы быстро приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="5ca89-148">The Getting Started wizard helps you set up a simple call menu to get you up and running quickly.</span></span> <span data-ttu-id="5ca89-149">Если у вас несколько телефонных номеров, для которых нужно настроить голосовое меню, или если нужно настроить более сложные голосовые меню (такая функция называется "автосекретарь"), см. [Настройка облачного автосекретаря](set-up-auto-attendants.md) после завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="5ca89-149">If you have multiple phone numbers that you want to set up call menus for or you want to set up more complex call menus (also called auto attendants), see [Set up a Cloud auto attendant](set-up-auto-attendants.md) after you finish the wizard.</span></span>

<table>
    <tr>
        <td> <p><span data-ttu-id="5ca89-150">Мастер начальной настройки использует введенные вами сведения и настраивает корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="5ca89-150">The Getting Started wizard takes the information that you enter and sets up Business Voice.</span></span> <span data-ttu-id="5ca89-151">На странице <b>Обзор</b> можно просмотреть, какие номера телефонов назначены пользователям, проверить голосовое меню, прослушать приветствие и т. д.</span><span class="sxs-lookup"><span data-stu-id="5ca89-151">On the <b>Overview</b> page, you can see what phone numbers are assigned to your users, look at your call menu, listen to your greeting, and more.</span></span></p>
             <p><span data-ttu-id="5ca89-152">Настройка занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5ca89-152">Setup takes several minutes.</span></span> <span data-ttu-id="5ca89-153">Если выбрать <b>Готово</b>, настройка корпоративной голосовой связи будет продолжена в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="5ca89-153">If you select <b>Done</b>, we'll continue to set up Business Voice in the background.</span></span> <span data-ttu-id="5ca89-154">Также можно просто дождаться завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="5ca89-154">Or just wait until setup is finished.</span></span> <span data-ttu-id="5ca89-155">После ее завершения перейдите в раздел <b>Голосовая связь</b> в <a href="https://admin.teams.microsoft.com" target="_blank">Центре администрирования Teams</a>, чтобы настроить дополнительные функции корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5ca89-155">After it's finished, go to <b>Voice</b> in the <a href="https://admin.teams.microsoft.com" target="_blank">Teams admin center</a> to set up more Business Voice features.</span></span></p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
