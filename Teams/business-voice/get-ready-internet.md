---
title: Проверка подключения к Интернету
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653555"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="58642-102">Проверка подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="58642-102">Check your Internet connection</span></span>

<span data-ttu-id="58642-103">Корпоративная голосовая связь находится в облаке с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58642-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="58642-104">Для всех компьютеров и устройств, использующих Microsoft Teams и корпоративную голосовую связь, требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="58642-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="58642-105">Для оптимальной работы с корпоративной голосовой связью требуется широкополосное подключение к Интернету, которое может поддерживать ожидаемое количество звонков, которые будут выполняться в любой фиксированный момент времени.</span><span class="sxs-lookup"><span data-stu-id="58642-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="58642-106">Также необходимо убедиться в том, что компьютеры в вашей сети могут получить доступ к серверам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58642-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="58642-107">Чтобы выполнить эти действия, необходимо наличие клиента с одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="58642-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="58642-108">Office 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="58642-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="58642-109">Office 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="58642-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="58642-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="58642-110">Office 365 E1</span></span>
* <span data-ttu-id="58642-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="58642-111">Office 365 E3</span></span>
* <span data-ttu-id="58642-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="58642-112">Office 365 F1</span></span>
* <span data-ttu-id="58642-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="58642-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="58642-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="58642-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="58642-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="58642-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="58642-116">Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="58642-116">Microsoft 365 Business</span></span>

<span data-ttu-id="58642-117">Для выполнения этих действий не требуется лицензия на корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="58642-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="58642-118">Проверьте скорость подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="58642-118">Check your Internet connection speed</span></span>

<span data-ttu-id="58642-119">Эта статья поможет вам определить, достаточно ли быстрое подключение к Интернету для тех пользователей, которым необходимо совершать телефонные звонки, проводить видеоконференции и т. д.</span><span class="sxs-lookup"><span data-stu-id="58642-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="58642-120">Вам потребуется ввести некоторые сведения о вашей организации и получить отчет о том, какая часть вашего подключения к Интернету будет использоваться Teams и корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="58642-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="58642-121">Получение сведений о подключении к Интернету и о пользователях</span><span class="sxs-lookup"><span data-stu-id="58642-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="58642-122">Прежде чем начать, необходимо уточнить следующее.</span><span class="sxs-lookup"><span data-stu-id="58642-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="58642-123">Скорость подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="58642-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="58642-124">Количество пользователей, которые будут использовать корпоративную голосовую связь в основном в офисе.</span><span class="sxs-lookup"><span data-stu-id="58642-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="58642-125">Количество пользователей, которые будут использовать корпоративную голосовую связь в основном из удаленных расположений, таких как домашний офис.</span><span class="sxs-lookup"><span data-stu-id="58642-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="58642-126">Ввод данных в планировщик сети</span><span class="sxs-lookup"><span data-stu-id="58642-126">Enter your information into the network planner</span></span>

<span data-ttu-id="58642-127">Вот что вам нужно будет сделать:</span><span class="sxs-lookup"><span data-stu-id="58642-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="58642-128">Откройте браузер, перейдите к https://admin.teams.microsoft.com и войдите в систему, используя учетную запись с правами глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="58642-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="58642-129">Учетная запись, которую вы использовали для регистрации в Office 365, имеет такие разрешения.</span><span class="sxs-lookup"><span data-stu-id="58642-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="58642-130">Откройте **Планирование** и выберите **Планировщик сети**.</span><span class="sxs-lookup"><span data-stu-id="58642-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="58642-131">В разделе **Планы сетей**выберите пункт **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="58642-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="58642-132">Присвойте вашему плану имя, а затем выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="58642-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="58642-133">Ваш план сети должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="58642-133">Your network plan should look like this:</span></span>

    ![Основной экран планировщика сети](../media/network-planner-main.png)
1. <span data-ttu-id="58642-135">Щелкните имя вашего плана сети (**Главный офис** на рисунке выше).</span><span class="sxs-lookup"><span data-stu-id="58642-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="58642-136">На следующей странице выберите **Добавить сетевой сайт** на вкладке **Сетевые сайты**.</span><span class="sxs-lookup"><span data-stu-id="58642-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="58642-137">Заполните только те поля, которые указаны на снимке экрана ниже, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="58642-137">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="58642-138">Оставьте пустыми остальные поля на этом экране и не выбирайте параметр **ExpressRoute** или **Подключено к глобальной сети**.</span><span class="sxs-lookup"><span data-stu-id="58642-138">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Сведения о сайте сетевого планировщика](../media/network-planner-site-info.png)
1. <span data-ttu-id="58642-140">На вкладке **Отчет** выберите **Запуск отчета**.</span><span class="sxs-lookup"><span data-stu-id="58642-140">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="58642-141">Заполните указанные ниже сведения, а затем нажмите кнопку **Создать отчет**. В нем будут отражены требования к пропускной способности для Teams.</span><span class="sxs-lookup"><span data-stu-id="58642-141">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="58642-142">Сведения о том, как прочитать отчет, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="58642-142">We'll show you how to read the report in the next section.</span></span>

    ![Сведения об отчете планировщика сети](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="58642-144">Определение минимальной скорости подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="58642-144">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="58642-145">При выборе команды **Создать отчет**, Office 365 создает отчет, который выглядит так:</span><span class="sxs-lookup"><span data-stu-id="58642-145">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Подробные сведения об отчете планировщика сети](../media/network-planner-report.png)

<span data-ttu-id="58642-147">Выделенное число показывает, какая часть вашего подключения к Интернету и корпоративной голосовой связи будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="58642-147">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="58642-148">Мы рекомендуем, чтобы это число составляло не более 30 % от общей скорости подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="58642-148">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="58642-149">Например, если подключение к Интернету составляет 60 Мбит/с, Teams и корпоративная голосовая связь должны занимать не более 18 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="58642-149">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="58642-150">Минимальную скорость подключения к Интернету можно определить, выполнив следующий расчет: `<highlighted number> / .3`.</span><span class="sxs-lookup"><span data-stu-id="58642-150">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="58642-151">При использовании выделенного числа на рисунке выше, расчетное значение будет составлять `4.6875 / .3 = 15.6`.</span><span class="sxs-lookup"><span data-stu-id="58642-151">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="58642-152">Это означает, что минимальная скорость подключения к Интернету должна быть не менее 15,6 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="58642-152">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="58642-153">Если Teams и корпоративная голосовая связь будут использовать более 30 % общей скорости подключения к Интернету, выделенное число будет отображаться красным цветом.</span><span class="sxs-lookup"><span data-stu-id="58642-153">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="58642-154">В таком случае вам может потребоваться обновить подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="58642-154">If this happens, you might need to upgrade your Internet connection.</span></span>

![Предупреждение о скорости подключения](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="58642-156">Убедитесь в том, что компьютеры и устройства в вашей сети могут получить доступ к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58642-156">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="58642-157">Для правильной работы компьютерам и устройствам, которые вы хотите использовать для корпоративной голосовой связи, необходимо взаимодействовать с серверами Microsoft 365, используя определенные сетевые порты.</span><span class="sxs-lookup"><span data-stu-id="58642-157">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="58642-158">Сетевые порты, в сущности, представляют собой “двери”, через которые компьютеры и устройства могут взаимодействовать друг с другом через сеть или Интернет.</span><span class="sxs-lookup"><span data-stu-id="58642-158">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="58642-159">Ваш брандмауэр должен разрешить компьютерам и устройствам в вашей сети доступ к Microsoft 365 через следующие исходящие сетевые порты:</span><span class="sxs-lookup"><span data-stu-id="58642-159">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="58642-160">**TCP-порты** 80 и 443</span><span class="sxs-lookup"><span data-stu-id="58642-160">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="58642-161">**UDP-порты** 3478, 3479, 3480 и 3481</span><span class="sxs-lookup"><span data-stu-id="58642-161">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="58642-162">Чтобы убедиться в том, что ваш брандмауэр разрешает взаимодействие через эти сетевые порты, проще всего выполнить тестовый звонок с помощью Teams.</span><span class="sxs-lookup"><span data-stu-id="58642-162">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="58642-163">Чтобы выполнить тестовый звонок, произведите указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="58642-163">To make a test call, do the following:</span></span>

1. <span data-ttu-id="58642-164">Перейдите к https://aka.ms/getteams на компьютере в вашей сети, чтобы установить Teams.</span><span class="sxs-lookup"><span data-stu-id="58642-164">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="58642-165">Убедитесь в том, что динамики и микрофон подключены к этому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="58642-165">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="58642-166">Открытие Teams и выполните вход с использованием учетной записи Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58642-166">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="58642-167">В Teams выберите свой аватар, а затем **Параметры** > **Устройства**</span><span class="sxs-lookup"><span data-stu-id="58642-167">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="58642-168">В разделе **Аудиоустройства** выберите **Выполнить тестовый звонок**</span><span class="sxs-lookup"><span data-stu-id="58642-168">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="58642-169">Следуйте инструкциям, чтобы оставить сообщение и прослушать его воспроизведение</span><span class="sxs-lookup"><span data-stu-id="58642-169">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="58642-170">Если звонок установлен и вы услышите воспроизведение вашего сообщения, ваш брандмауэр настроен правильно.</span><span class="sxs-lookup"><span data-stu-id="58642-170">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="58642-171">Если звонок установлен, но вы не слышите инструкции или воспроизведение вашего сообщения, проверьте, правильно ли настроены ваши динамики и микрофон, и распознаются ли они компьютером.</span><span class="sxs-lookup"><span data-stu-id="58642-171">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="58642-172">Повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="58642-172">Try again.</span></span>
* <span data-ttu-id="58642-173">Если звонок не подключается, или же звонок подключается, но вы не слышите воспроизведение вашего сообщения, возможно, вам потребуется обновить брандмауэр, чтобы разрешить указанные выше сетевые порты.</span><span class="sxs-lookup"><span data-stu-id="58642-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="58642-174">Проверьте в документации вашего брандмауэра, как разрешить сетевым портам подключаться к Интернету, или обратитесь за помощью к ИТ-специалисту.</span><span class="sxs-lookup"><span data-stu-id="58642-174">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="58642-175">Если вы ИТ-специалист и хотите узнать больше о том, как подготовить крупные или более сложные сети для поддержки корпоративной голосовой связи, ознакомьтесь со статьей [Оценка среды](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="58642-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="58642-176">Статья [Оценка среды](../3-envision-evaluate-my-environment.md) содержит дополнительные сведения о требованиях к пропускной способности, прокси-серверу и брандмауэру, а также о том, как проверить свою сеть с помощью [Средства оценки сети](../3-envision-evaluate-my-environment.md#test-the-network).</span><span class="sxs-lookup"><span data-stu-id="58642-176">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
