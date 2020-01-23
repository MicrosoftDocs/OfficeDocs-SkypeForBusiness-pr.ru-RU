---
title: Проверка подключения к Интернету для корпоративной голосовой связи
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
ms.openlocfilehash: 17eca42d01bcfb8a6b440c16408f31f6301b0338
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268715"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="9a43b-102">Проверка подключения к Интернету для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9a43b-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="9a43b-103">Корпоративная голосовая связь находится в облаке с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a43b-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="9a43b-104">Для всех устройств, использующих Microsoft Teams и корпоративную голосовую связь, требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9a43b-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="9a43b-105">Для оптимальной работы с корпоративной голосовой связью требуется широкополосное подключение к Интернету, которое может поддерживать максимальное количество звонков, которое может выполняться в любой фиксированный момент времени в организации.</span><span class="sxs-lookup"><span data-stu-id="9a43b-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="9a43b-106">Также необходимо убедиться, что компьютеры в вашей сети могут получить доступ к серверам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a43b-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="9a43b-107">Чтобы выполнить эти действия, необходимо наличие клиента с одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="9a43b-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="9a43b-108">Office 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="9a43b-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="9a43b-109">Office 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="9a43b-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="9a43b-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="9a43b-110">Office 365 E1</span></span>
* <span data-ttu-id="9a43b-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="9a43b-111">Office 365 E3</span></span>
* <span data-ttu-id="9a43b-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="9a43b-112">Office 365 F1</span></span>
* <span data-ttu-id="9a43b-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="9a43b-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="9a43b-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="9a43b-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="9a43b-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="9a43b-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="9a43b-116">Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="9a43b-116">Microsoft 365 Business</span></span>

<span data-ttu-id="9a43b-117">Для выполнения этих действий не требуется лицензия на корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="9a43b-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="9a43b-118">Проверьте скорость подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="9a43b-118">Check your Internet connection speed</span></span>

<span data-ttu-id="9a43b-119">Эта статья поможет определить, достаточно ли быстрое подключение к Интернету для пользователей, которым необходимо совершать телефонные звонки и проводить видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="9a43b-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="9a43b-120">Вам нужно указать сведения о вашей организации и получить отчет о том, какая часть вашего подключения к Интернету будет использоваться Teams и корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="9a43b-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="9a43b-121">Сбор сведений о подключении к Интернету и о пользователях</span><span class="sxs-lookup"><span data-stu-id="9a43b-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="9a43b-122">Перед началом вам требуется следующая информация:</span><span class="sxs-lookup"><span data-stu-id="9a43b-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="9a43b-123">Скорость подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="9a43b-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="9a43b-124">Количество пользователей, которые будут использовать корпоративную голосовую связь в основном в офисе</span><span class="sxs-lookup"><span data-stu-id="9a43b-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="9a43b-125">Количество пользователей, которые будут использовать корпоративную голосовую связь в основном из удаленных расположений, таких как домашний офис</span><span class="sxs-lookup"><span data-stu-id="9a43b-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="9a43b-126">Ввод данных в планировщик сети</span><span class="sxs-lookup"><span data-stu-id="9a43b-126">Enter your information into the network planner</span></span>

<span data-ttu-id="9a43b-127">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a43b-127">Follow these steps:</span></span>

1. <span data-ttu-id="9a43b-128">В браузере перейдите по адресу https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9a43b-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="9a43b-129">Выполните вход, используя учетную запись с правами глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="9a43b-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="9a43b-130">Учетная запись, которую вы использовали для регистрации в Office 365, имеет такие разрешения.</span><span class="sxs-lookup"><span data-stu-id="9a43b-130">The account you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="9a43b-131">Откройте **Планирование** и выберите **Планировщик сети**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-131">Open **Planning** and then select **Network planner**.</span></span>
3. <span data-ttu-id="9a43b-132">В разделе **Планы сетей** выберите пункт **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="9a43b-133">Укажите имя для плана и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="9a43b-134">Ваш план сети должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="9a43b-134">Your network plan should look like this:</span></span>

    ![Основной экран планировщика сети](../media/network-planner-main.png)
1. <span data-ttu-id="9a43b-136">Выберите имя плана сети.</span><span class="sxs-lookup"><span data-stu-id="9a43b-136">Select the name of your network plan.</span></span> <span data-ttu-id="9a43b-137">(Это **Главный офис** на предыдущем изображении.)</span><span class="sxs-lookup"><span data-stu-id="9a43b-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="9a43b-138">На следующей странице выберите **Добавить сетевой сайт** на вкладке **Сетевые сайты**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-138">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
3. <span data-ttu-id="9a43b-139">Заполните только те поля, которые указаны на снимке экрана ниже, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-139">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="9a43b-140">Оставьте пустыми остальные поля на этом экране и не выбирайте параметр **ExpressRoute** или **Подключено к глобальной сети**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-140">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Сведения о сайте сетевого планировщика](../media/network-planner-site-info.png)
1. <span data-ttu-id="9a43b-142">На вкладке **Отчет** нажмите кнопку **Создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-142">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="9a43b-143">Введите указанные ниже сведения и нажмите кнопку **Создать отчет**. В отчете будут отражены требования к пропускной способности для Teams.</span><span class="sxs-lookup"><span data-stu-id="9a43b-143">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="9a43b-144">Сведения о том, как прочитать отчет, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="9a43b-144">We'll show you how to read the report in the next section.</span></span>

    ![Сведения об отчете планировщика сети](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="9a43b-146">Определение минимальной скорости подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="9a43b-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="9a43b-147">При выборе команды **Создать отчет**, Office 365 создает отчет, который выглядит так:</span><span class="sxs-lookup"><span data-stu-id="9a43b-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Подробные сведения об отчете планировщика сети](../media/network-planner-report.png)

<span data-ttu-id="9a43b-149">Выделенное число показывает, какая часть вашего подключения к Интернету и корпоративной голосовой связи будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="9a43b-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="9a43b-150">Мы рекомендуем, чтобы это число составляло не более 30 процентов от общей скорости подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9a43b-150">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="9a43b-151">Например, если подключение к Интернету составляет 60 Мбит/с, Teams и корпоративная голосовая связь должны использовать не более 18 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="9a43b-151">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="9a43b-152">Минимальную скорость подключения к Интернету можно определить с помощью следующей формулы: *\<выделенное число> / 0,3*.</span><span class="sxs-lookup"><span data-stu-id="9a43b-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="9a43b-153">С использованием выделенного числа на предыдущем рисунке расчетное значение будет составлять *4,6875 / 0,3 = 15,6*.</span><span class="sxs-lookup"><span data-stu-id="9a43b-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="9a43b-154">В этом случае скорость подключения к Интернету должна составлять не менее 15,6 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="9a43b-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="9a43b-155">Если Teams и корпоративная голосовая связь будут использовать более 30 процентов общей скорости подключения к Интернету, выделенное число будет отображаться красным цветом.</span><span class="sxs-lookup"><span data-stu-id="9a43b-155">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="9a43b-156">В таком случае вам может потребоваться обновить подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9a43b-156">In that case, you may need to upgrade your Internet connection.</span></span>

![Предупреждение о скорости подключения](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="9a43b-158">Убедитесь, что компьютеры и устройства в вашей сети могут получить доступ к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a43b-158">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="9a43b-159">Компьютеры и устройства, использующие корпоративную голосовую связь, должны применять определенные сетевые порты для взаимодействия с серверами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a43b-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="9a43b-160">Эти порты, в сущности, представляют собой "двери", через которые устройства взаимодействуют друг с другом через сеть или Интернет.</span><span class="sxs-lookup"><span data-stu-id="9a43b-160">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="9a43b-161">Ваш брандмауэр должен разрешить устройствам в вашей сети доступ к Microsoft 365 через следующие *исходящие* сетевые порты:</span><span class="sxs-lookup"><span data-stu-id="9a43b-161">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="9a43b-162">**TCP-порты** 80 и 443</span><span class="sxs-lookup"><span data-stu-id="9a43b-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="9a43b-163">**UDP-порты** 3478, 3479, 3480 и 3481</span><span class="sxs-lookup"><span data-stu-id="9a43b-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="9a43b-164">Чтобы убедиться, что ваш брандмауэр разрешает взаимодействие через эти сетевые порты, проще всего выполнить тестовый звонок в Teams:</span><span class="sxs-lookup"><span data-stu-id="9a43b-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span>

1. <span data-ttu-id="9a43b-165">Перейдите по адресу https://aka.ms/getteams на компьютере в вашей сети и установите Teams.</span><span class="sxs-lookup"><span data-stu-id="9a43b-165">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="9a43b-166">Убедитесь, что у компьютера есть динамики и микрофон.</span><span class="sxs-lookup"><span data-stu-id="9a43b-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="9a43b-167">Откройте Teams и выполните вход с использованием учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a43b-167">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="9a43b-168">В Teams щелкните свой аватар и выберите **Настройки** > **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-168">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="9a43b-169">В разделе **Звуковые устройства** нажмите кнопку **Сделать пробный звонок**.</span><span class="sxs-lookup"><span data-stu-id="9a43b-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="9a43b-170">Следуйте инструкциям, чтобы оставить сообщение и прослушать его воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="9a43b-170">Follow the prompts to leave a message and have it played back to you</span></span>

   * <span data-ttu-id="9a43b-171">Если звонок установлен и вы слышите свое сообщение, ваш брандмауэр настроен правильно.</span><span class="sxs-lookup"><span data-stu-id="9a43b-171">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="9a43b-172">Если звонок установлен, но вы не слышите инструкции или свое сообщение, проверьте, правильно ли настроены ваши динамики и микрофон, и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="9a43b-172">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span>
   * <span data-ttu-id="9a43b-173">Если звонок не подключается, или же звонок подключается, но вы не слышите свое сообщение, вам может понадобиться обновить брандмауэр, чтобы разрешить доступ к требуемым сетевым портам.</span><span class="sxs-lookup"><span data-stu-id="9a43b-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="9a43b-174">Проверьте документацию своего брандмауэра или обратитесь за помощью к ИТ-специалисту.</span><span class="sxs-lookup"><span data-stu-id="9a43b-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="9a43b-175">Если вы ИТ-специалист и хотите узнать больше о том, как подготовить крупные или более сложные сети для поддержки корпоративной голосовой связи, см. статью [Оценка среды](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9a43b-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="9a43b-176">Эта статья содержит сведения о требованиях к пропускной способности, прокси-серверу и брандмауэру, а также об использовании [Средства оценки сети](../3-envision-evaluate-my-environment.md#test-the-network) для проверки сети.</span><span class="sxs-lookup"><span data-stu-id="9a43b-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

