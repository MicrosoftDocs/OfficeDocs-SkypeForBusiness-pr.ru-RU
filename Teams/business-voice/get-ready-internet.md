---
title: Проверка подключения к Интернету для корпоративной голосовой связи
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
ms.openlocfilehash: 473c053036b766ef475c3aed5f0bba2d24dd9e6c
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824887"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="293a1-102">Проверка подключения к Интернету для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="293a1-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="293a1-103">Корпоративная голосовая связь находится в облаке с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="293a1-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="293a1-104">Для всех устройств, использующих Microsoft Teams и корпоративную голосовую связь, требуется подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="293a1-104">Every device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="293a1-105">Для оптимальной работы с корпоративной голосовой связью требуется широкополосное подключение к Интернету, которое может поддерживать максимальное количество звонков, которое может выполняться в любой фиксированный момент времени в организации.</span><span class="sxs-lookup"><span data-stu-id="293a1-105">To get the best Business Voice experience, you need a broadband Internet connection that can support the maximum number of phone calls that your organization might make at any one time.</span></span> <span data-ttu-id="293a1-106">Также необходимо убедиться, что компьютеры в вашей сети могут получить доступ к серверам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="293a1-106">You also need to make sure that the computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="293a1-107">Чтобы выполнить эти действия, необходимо наличие клиента с одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="293a1-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="293a1-108">Office 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="293a1-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="293a1-109">Office 365 бизнес премиум</span><span class="sxs-lookup"><span data-stu-id="293a1-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="293a1-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="293a1-110">Office 365 E1</span></span>
* <span data-ttu-id="293a1-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="293a1-111">Office 365 E3</span></span>
* <span data-ttu-id="293a1-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="293a1-112">Office 365 F1</span></span>
* <span data-ttu-id="293a1-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="293a1-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="293a1-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="293a1-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="293a1-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="293a1-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="293a1-116">Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="293a1-116">Microsoft 365 Business</span></span>

<span data-ttu-id="293a1-117">Для выполнения этих действий не требуется лицензия на корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="293a1-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="293a1-118">Проверьте скорость подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="293a1-118">Check your Internet connection speed</span></span>

<span data-ttu-id="293a1-119">Эта статья поможет определить, достаточно ли быстрое подключение к Интернету для пользователей, которым необходимо совершать телефонные звонки и проводить видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="293a1-119">This article helps determine whether your Internet connection is fast enough for the number of people who need to make phone calls and host video conferences.</span></span> <span data-ttu-id="293a1-120">Вам нужно указать сведения о вашей организации и получить отчет о том, какая часть вашего подключения к Интернету будет использоваться Teams и корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="293a1-120">You'll provide information about your organization and get back a report that shows how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="293a1-121">Сбор сведений о подключении к Интернету и о пользователях</span><span class="sxs-lookup"><span data-stu-id="293a1-121">Gather information about your Internet connection and users</span></span>

<span data-ttu-id="293a1-122">Перед началом вам требуется следующая информация:</span><span class="sxs-lookup"><span data-stu-id="293a1-122">Before you start, you need the following information:</span></span>

* <span data-ttu-id="293a1-123">Скорость подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="293a1-123">The speed of your Internet connection</span></span>
* <span data-ttu-id="293a1-124">Количество пользователей, которые будут использовать корпоративную голосовую связь в основном в офисе</span><span class="sxs-lookup"><span data-stu-id="293a1-124">How many people will use Business Voice mainly from your office</span></span>
* <span data-ttu-id="293a1-125">Количество пользователей, которые будут использовать корпоративную голосовую связь в основном из удаленных расположений, таких как домашний офис</span><span class="sxs-lookup"><span data-stu-id="293a1-125">How many people will use Business Voice mainly from a remote location, such as a home office</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="293a1-126">Ввод данных в планировщик сети</span><span class="sxs-lookup"><span data-stu-id="293a1-126">Enter your information into the network planner</span></span>

<span data-ttu-id="293a1-127">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="293a1-127">Follow these steps:</span></span>

1. <span data-ttu-id="293a1-128">В браузере перейдите по адресу https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="293a1-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="293a1-129">Выполните вход, используя учетную запись с правами глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="293a1-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="293a1-130">Учетная запись, которую вы использовали для регистрации в Office 365, имеет такие разрешения.</span><span class="sxs-lookup"><span data-stu-id="293a1-130">The account that you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="293a1-131">Откройте **Планирование** и выберите **Планировщик сети**.</span><span class="sxs-lookup"><span data-stu-id="293a1-131">Open **Planning** and select **Network planner**.</span></span>
3. <span data-ttu-id="293a1-132">В разделе **Планы сетей** выберите пункт **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="293a1-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="293a1-133">Укажите имя для плана и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="293a1-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="293a1-134">Ваш план сети должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="293a1-134">Your network plan should look like this:</span></span>

    ![Основной экран планировщика сети](../media/network-planner-main.png)
1. <span data-ttu-id="293a1-136">Выберите имя плана сети.</span><span class="sxs-lookup"><span data-stu-id="293a1-136">Select the name of your network plan.</span></span> <span data-ttu-id="293a1-137">(Это **Главный офис** на предыдущем изображении.)</span><span class="sxs-lookup"><span data-stu-id="293a1-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="293a1-138">На следующей странице выберите **Добавить сетевой сайт** на вкладке **Сетевые сайты**.</span><span class="sxs-lookup"><span data-stu-id="293a1-138">On the next page, select **Add a network site** on the **Network sites** tab.</span></span>
3. <span data-ttu-id="293a1-139">Заполните только те поля, которые указаны на снимке экрана ниже, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="293a1-139">Fill in only the fields that are indicated in the following screenshot, and then select **Save**.</span></span> <span data-ttu-id="293a1-140">Оставьте пустыми остальные поля на этом экране и не выбирайте параметр **ExpressRoute** или **Подключено к глобальной сети**.</span><span class="sxs-lookup"><span data-stu-id="293a1-140">Leave the other fields on this screen blank, and don't select the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![Сведения о сайте сетевого планировщика](../media/network-planner-site-info.png)
1. <span data-ttu-id="293a1-142">На вкладке **Отчет** нажмите кнопку **Создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="293a1-142">On the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="293a1-143">Введите указанные ниже сведения и нажмите кнопку **Создать отчет**. В отчете будут отражены требования к пропускной способности для Teams.</span><span class="sxs-lookup"><span data-stu-id="293a1-143">Enter the following information, and then select **Generate report** to create a report that shows the bandwidth requirements for Teams.</span></span> <span data-ttu-id="293a1-144">Сведения о том, как прочитать отчет, см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="293a1-144">We show you how to read the report in the next section.</span></span>

    ![Сведения об отчете планировщика сети](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="293a1-146">Определение минимальной скорости подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="293a1-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="293a1-147">При выборе команды **Создать отчет**, Office 365 создает отчет, который выглядит так:</span><span class="sxs-lookup"><span data-stu-id="293a1-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![Подробные сведения об отчете планировщика сети](../media/network-planner-report.png)

<span data-ttu-id="293a1-149">Выделенное число показывает, какая часть вашего подключения к Интернету и корпоративной голосовой связи будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="293a1-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="293a1-150">Мы рекомендуем, чтобы это число составляло не более 30 процентов от общей скорости подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="293a1-150">We recommend that this number is no more than 30 percent of your total Internet connection speed.</span></span> <span data-ttu-id="293a1-151">Например, если подключение к Интернету составляет 60 Мбит/с, Teams и корпоративная голосовая связь должны использовать не более 18 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="293a1-151">For example, if your Internet connection is 60 Mbps, Teams and Business Voice should use no more than 18 Mbps.</span></span>

<span data-ttu-id="293a1-152">Минимальную скорость подключения к Интернету можно определить с помощью следующей формулы: *\<выделенное число> / 0,3*.</span><span class="sxs-lookup"><span data-stu-id="293a1-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="293a1-153">С использованием выделенного числа на предыдущем рисунке расчетное значение будет составлять *4,6875 / 0,3 = 15,6*.</span><span class="sxs-lookup"><span data-stu-id="293a1-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="293a1-154">В этом случае скорость подключения к Интернету должна составлять не менее 15,6 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="293a1-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="293a1-155">Если Teams и корпоративная голосовая связь будут использовать более 30 процентов общей скорости подключения к Интернету, выделенное число будет отображаться красным цветом.</span><span class="sxs-lookup"><span data-stu-id="293a1-155">If Teams and Business Voice will use more than 30 percent of your total Internet connection speed, the highlighted number will appear red.</span></span> <span data-ttu-id="293a1-156">В таком случае вам может потребоваться обновить подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="293a1-156">In that case, you may need to upgrade your Internet connection.</span></span>

![Предупреждение о скорости подключения](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="293a1-158">Убедитесь, что компьютеры и устройства в вашей сети могут получить доступ к Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="293a1-158">Make sure the computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="293a1-159">Компьютеры и устройства, использующие корпоративную голосовую связь, должны применять определенные сетевые порты для взаимодействия с серверами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="293a1-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="293a1-160">Эти порты, в сущности, представляют собой "двери", через которые устройства взаимодействуют друг с другом через сеть или Интернет.</span><span class="sxs-lookup"><span data-stu-id="293a1-160">These ports are essentially doors through which devices talk to each other over a network or the Internet.</span></span> <span data-ttu-id="293a1-161">Ваш брандмауэр должен разрешить устройствам в вашей сети доступ к Microsoft 365 через следующие *исходящие* сетевые порты:</span><span class="sxs-lookup"><span data-stu-id="293a1-161">Your firewall needs to allow devices on your network to reach Microsoft 365 through the following *outbound* network ports:</span></span>

* <span data-ttu-id="293a1-162">**TCP-порты** 80 и 443</span><span class="sxs-lookup"><span data-stu-id="293a1-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="293a1-163">**UDP-порты** 3478, 3479, 3480 и 3481</span><span class="sxs-lookup"><span data-stu-id="293a1-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="293a1-164">Чтобы убедиться, что ваш брандмауэр разрешает взаимодействие через эти сетевые порты, проще всего выполнить тестовый звонок в Teams:</span><span class="sxs-lookup"><span data-stu-id="293a1-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call in Teams:</span></span>

1. <span data-ttu-id="293a1-165">Перейдите по адресу https://aka.ms/getteams на компьютере в вашей сети и установите Teams.</span><span class="sxs-lookup"><span data-stu-id="293a1-165">Go to https://aka.ms/getteams on a computer on your network and install Teams.</span></span> <span data-ttu-id="293a1-166">Убедитесь, что у компьютера есть динамики и микрофон.</span><span class="sxs-lookup"><span data-stu-id="293a1-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="293a1-167">Откройте Teams и выполните вход с использованием учетной записи Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="293a1-167">Open Teams and sign in by using a Microsoft 365 account.</span></span>
3. <span data-ttu-id="293a1-168">В Teams щелкните свой аватар и выберите **Настройки** > **Устройства**.</span><span class="sxs-lookup"><span data-stu-id="293a1-168">In Teams, select your profile picture, and then go to **Settings** > **Devices**.</span></span>
4. <span data-ttu-id="293a1-169">В разделе **Звуковые устройства** нажмите кнопку **Сделать пробный звонок**.</span><span class="sxs-lookup"><span data-stu-id="293a1-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="293a1-170">Следуйте инструкциям, чтобы оставить сообщение и прослушать его воспроизведение.</span><span class="sxs-lookup"><span data-stu-id="293a1-170">Follow the steps to leave a message and have it played back to you.</span></span>

   * <span data-ttu-id="293a1-171">Если звонок установлен и вы слышите свое сообщение, ваш брандмауэр настроен правильно.</span><span class="sxs-lookup"><span data-stu-id="293a1-171">If the call connects and you hear your message, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="293a1-172">Если звонок установлен, но вы не слышите инструкции или свое сообщение, проверьте, правильно ли настроены ваши динамики и микрофон, и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="293a1-172">If the call connects, but you can't hear the instructions or your message, make sure that your speakers and microphone are set up correctly, and then try again.</span></span>
   * <span data-ttu-id="293a1-173">Если звонок не подключается, или же звонок подключается, но вы не слышите свое сообщение, вам может понадобиться обновить брандмауэр, чтобы разрешить доступ к требуемым сетевым портам.</span><span class="sxs-lookup"><span data-stu-id="293a1-173">If the call doesn't connect or it connects but you can't hear your message, you might need to update your firewall to allow access to the required network ports.</span></span> <span data-ttu-id="293a1-174">Проверьте документацию своего брандмауэра или обратитесь за помощью к ИТ-специалисту.</span><span class="sxs-lookup"><span data-stu-id="293a1-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="293a1-175">Если вы ИТ-специалист и хотите узнать больше о том, как подготовить крупные или более сложные сети для поддержки корпоративной голосовой связи, см. статью [Оценка среды](../3-envision-evaluate-my-environment.md).</span><span class="sxs-lookup"><span data-stu-id="293a1-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, see [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="293a1-176">Эта статья содержит сведения о требованиях к пропускной способности, прокси-серверу и брандмауэру, а также об использовании [Средства оценки сети](../3-envision-evaluate-my-environment.md#test-the-network) для проверки сети.</span><span class="sxs-lookup"><span data-stu-id="293a1-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

