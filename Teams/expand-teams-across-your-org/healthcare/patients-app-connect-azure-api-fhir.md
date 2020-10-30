---
title: Подключение приложения для пациентов к Azure API для FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Сведения о том, как подключить приложение пациентов в Microsoft Teams к Azure API для FHIR (ресурсы для быстрого обеспечения для сферы здравоохранения).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 29447791a8ba169bfc50173b249b3f8b987c7a17
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803557"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="1a996-103">Подключение приложения для пациентов к Azure API для FHIR</span><span class="sxs-lookup"><span data-stu-id="1a996-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="1a996-104">Действительно 30 октября 2020 г. приложение пациентов было прекращено и заменено [приложением "списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) " в Teams.</span><span class="sxs-lookup"><span data-stu-id="1a996-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="1a996-105">Данные приложения пациентов хранятся в почтовом ящике группы Office 365, которая является резервной командой.</span><span class="sxs-lookup"><span data-stu-id="1a996-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="1a996-106">Все данные, связанные с приложением пациентов, сохраняются в этой группе, но их больше нельзя будет получить с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1a996-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="1a996-107">Пользователи могут повторно создавать списки с помощью приложения " [списки](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)".</span><span class="sxs-lookup"><span data-stu-id="1a996-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="1a996-108">Благодаря спискам, благодаря вашим командам в организации здравоохранения вы сможете создавать списки пациент для сценариев, начиная с округляющих и interdisciplinaryных собраний групп и заканчивая общим мониторингом пациента.</span><span class="sxs-lookup"><span data-stu-id="1a996-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="1a996-109">Чтобы приступить к работе, изучите шаблон пациентов в списках.</span><span class="sxs-lookup"><span data-stu-id="1a996-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="1a996-110">Дополнительные сведения об управлении приложением Lists в Организации можно найти в разделе [Управление приложением "списки"](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="1a996-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="1a996-111">Выполните эти действия, чтобы разрешить приложению пациентов в Microsoft Teams получить доступ к интерфейсу API Azure для экземпляра FHIR.</span><span class="sxs-lookup"><span data-stu-id="1a996-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="1a996-112">В этой статье предполагается, что у вас есть [API Azure для настройки экземпляра FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) и его настройки в клиенте.</span><span class="sxs-lookup"><span data-stu-id="1a996-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="1a996-113">Если вы еще не создали интерфейс Azure API для экземпляра FHIR в клиенте, ознакомьтесь [со ссылкой краткое руководство: развертывание Azure API для FHIR с помощью портала Azure](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="1a996-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="1a996-114">Щелкните [здесь](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) , чтобы предоставить согласие администратора для приложения пациентов.</span><span class="sxs-lookup"><span data-stu-id="1a996-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="1a996-115">При появлении соответствующего запроса войдите в систему с помощью учетной записи администратора клиента или глобального администратора, а затем нажмите кнопку " **подтвердить** ", чтобы предоставить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="1a996-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Снимок экрана: запрос разрешений для приложения пациентов](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="1a996-117">После того как вы согласны, закройте окно.</span><span class="sxs-lookup"><span data-stu-id="1a996-117">After you accept, close the window.</span></span> <span data-ttu-id="1a996-118">Вы увидите страницу, которая может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="1a996-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="1a996-119">Вы можете пропустить сообщение об ошибке на странице.</span><span class="sxs-lookup"><span data-stu-id="1a996-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="1a996-120">Это не так и означает, что разрешение предоставлено.</span><span class="sxs-lookup"><span data-stu-id="1a996-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="1a996-121">(Мы работаем с более удобной для пользователя страницей для этого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1a996-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="1a996-122">Оставайтесь на связи!)</span><span class="sxs-lookup"><span data-stu-id="1a996-122">Stay tuned!)</span></span>

    ![Снимок экрана: запрос разрешения для приложения пациентов](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="1a996-124">Войдите на [портал Azure](https://portal.azure.com) с учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="1a996-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="1a996-125">На панели навигации слева выберите пункт **Azure Active Directory** , а затем — **корпоративное приложение** .</span><span class="sxs-lookup"><span data-stu-id="1a996-125">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="1a996-126">Найдите строку с именем **пациентов (dev)** , а затем скопируйте значение из СТОЛБЦА " **код объекта** " в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1a996-126">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Снимок экрана: строка пациентов (dev) на портале Azure](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="1a996-128">Перейдите в Azure API для экземпляра ресурса FHIR, к которому нужно подключить приложение пациентов (путем его поиска или обзора ресурсов), а затем откройте параметры для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1a996-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Снимок экрана: API Azure для параметров экземпляра FHIR на портале Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="1a996-130">Нажмите кнопку **Проверка подлинности** , а затем вставьте код объекта, скопированный в действии 3, в поле **Разрешенные идентификаторы объектов** .</span><span class="sxs-lookup"><span data-stu-id="1a996-130">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="1a996-131">Это позволяет приложению пациентов получить доступ к серверу FHIR.</span><span class="sxs-lookup"><span data-stu-id="1a996-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="1a996-132">После вставки идентификатора объекта Azure Active Directory проверит его, и рядом с ним появится зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="1a996-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Снимок экрана: параметры проверки подлинности на портале Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="1a996-134">Нажмите кнопку **Сохранить** .</span><span class="sxs-lookup"><span data-stu-id="1a996-134">Click **Save** .</span></span> <span data-ttu-id="1a996-135">Это повторно развертывает экземпляр, который может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="1a996-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="1a996-136">Нажмите кнопку **Обзор** и скопируйте URL-адрес из **конечной точки метаданных FHIR** .</span><span class="sxs-lookup"><span data-stu-id="1a996-136">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="1a996-137">Удалите тег metadata, чтобы получить URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="1a996-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="1a996-138">Например, https://test02-teamshealth.azurehealthcareapis.com/ .</span><span class="sxs-lookup"><span data-stu-id="1a996-138">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Снимок экрана: конечная точка метаданных на портале Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="1a996-140">В Teams перейдите к экземпляру приложения пациентов, которое загружено в команду, щелкните **Параметры** , а затем в поле **ссылка** введите URL-адрес конечной точки сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="1a996-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="1a996-141">Затем нажмите кнопку **Подключение** , чтобы установить соединение и найти пациентов в списке.</span><span class="sxs-lookup"><span data-stu-id="1a996-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Снимок экрана: параметры приложения пациентов в Teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="1a996-143">Если вы получаете сообщение об ошибке при подключении к Teams на этом этапе, отправьте подробный снимок экрана с сообщением об ошибке, журналы из [Fiddler](https://www.telerik.com/download/fiddler) и другие шаги по воспроизводитию в сообщении электронной почты с темой "пациентов App-EMR" устранения неполадок "для [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1a996-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a996-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1a996-144">Related topics</span></span>

- [<span data-ttu-id="1a996-145">Обзор приложения для пациентов</span><span class="sxs-lookup"><span data-stu-id="1a996-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="1a996-146">Интеграция электронных историй болезни в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a996-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
