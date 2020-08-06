---
title: Gerenciador de conexões do Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSCM.F1
- SQL11.DTS.DESIGNER.AFPADLSCM.F1
ms.assetid: 7f1323f9-9dc3-4378-9c70-bbc65bfeabfd
author: yualan
ms.author: chugu
ms.openlocfilehash: 1ab6e90aad6472cc10bbb12cf4ca17def501bf00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684833"
---
# <a name="azure-data-lake-store-connection-manager"></a><span data-ttu-id="1a053-102">Gerenciador de conexões do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="1a053-102">Azure Data Lake Store Connection Manager</span></span>
  <span data-ttu-id="1a053-103">O **Gerenciador de conexões de Azure Data Lake Store** permite que um pacote SSIS se conecte a um serviço do Azure Data Lake Store por meio de dois tipos de autenticação: identidade de usuário do Azure AD e a identidade de serviço do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1a053-103">The **Azure Data Lake Store connection manager** enables an SSIS package to connect to an Azure Data Lake Store service through two authentication types: Azure AD User Identity and Azure AD Service Identity.</span></span>  

## <a name="configure-the-azure-data-lake-store-connection-manager"></a><span data-ttu-id="1a053-104">Configurar o Gerenciador de conexões do Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="1a053-104">Configure the Azure Data Lake Store Connection Manager</span></span> 
  
1.  <span data-ttu-id="1a053-105">Na caixa de diálogo **Adicionar gerenciador de conexões do SSIS** , selecione **AzureDataLake**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1a053-105">In the **Add SSIS Connection Manager** dialog box, select **AzureDataLake**, and click **Add**.</span></span>   
  
2.  <span data-ttu-id="1a053-106">Na caixa de diálogo Editor de Gerenciador de conexões do Azure Data Lake Store, digite a URL do host do armazenamento do Azure Data Lake Store no campo **Host ADLS** .</span><span class="sxs-lookup"><span data-stu-id="1a053-106">In the Azure Data Lake Store Connection Manager Editor dialog box, type in the Azure Data Lake Store host URL in **ADLS Host** field.</span></span> <span data-ttu-id="1a053-107">Por exemplo: https: \/ /Test.azuredatalakestore.net ou Test.azuredatalakestore.net.</span><span class="sxs-lookup"><span data-stu-id="1a053-107">For example: https:\//test.azuredatalakestore.net or test.azuredatalakestore.net.</span></span>
  
3.  <span data-ttu-id="1a053-108">Escolha o tipo de autenticação correspondente para acessar dados do Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="1a053-108">Choose corresponding authentication type to access Azure Data Lake Store data.</span></span>

    1.  <span data-ttu-id="1a053-109">Se você selecionou a opção de autenticação por **identidade de usuário do Azure AD** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1a053-109">If you selected **Azure AD User Identity** authentication option, do the following:</span></span>

        1. <span data-ttu-id="1a053-110">Especifique os valores para o **nome de usuário** e o campo de **senha** .</span><span class="sxs-lookup"><span data-stu-id="1a053-110">Specify values for the **User Name** and **Password** field.</span></span> 
    
        2. <span data-ttu-id="1a053-111">Clique no botão **Testar Conexão** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="1a053-111">Click **Test Connection** button to test the connection.</span></span> <span data-ttu-id="1a053-112">Se você e o administrador de locatários não deixaram SSIS acessar os dados do Azure Data Lake Store antes, você precisará clicar no botão **Aceitar** para SSIS acessar os dados do Azure Data Lake Store na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1a053-112">If you and your tenant administrator didn't consent SSIS to access your Azure Data Lake Store data before, you need click **Accept** button to consent SSIS to access your Azure Data Lake Store data in the pop out dialog.</span></span> <span data-ttu-id="1a053-113">Para obter mais informações sobre esta experiência de consentimento, consulte [integrando aplicativos com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="1a053-113">For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span></span>
    
        > [!NOTE] 
        > <span data-ttu-id="1a053-114">Para a opção de autenticação por Identidade do Usuário do Azure AD, a autenticação multifator e a conta da Microsoft não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="1a053-114">For Azure AD User Identity authentication option, multi-factor authentication and Microsoft account is NOT supported.</span></span>
    
    2.  <span data-ttu-id="1a053-115">Se você selecionou a opção de autenticação por **identidade de serviço do Azure AD** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1a053-115">If you selected **Azure AD Service Identity** authentication option, do the following:</span></span>
        1. <span data-ttu-id="1a053-116">Crie um aplicativo AAD e uma entidade de serviço que pode acessar os recursos do Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="1a053-116">Create an AAD application and service principal that can access Azure Data Lake resources.</span></span>
    
        2. <span data-ttu-id="1a053-117">Atribua este aplicativo AAD correspondente permissões para acessar os recursos do Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="1a053-117">Assign this AAD application corresponding permissions to access your Azure Data Lake resources.</span></span> <span data-ttu-id="1a053-118">Para obter mais informações sobre essa opção de autenticação, consulte [Use o portal para criar a entidade de serviço e o aplicativo do Active Directory que pode acessar recursos](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="1a053-118">For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>
    
        3. <span data-ttu-id="1a053-119">Especifique valores para **Id do cliente**, **chave secreta** e **nome do locatário** .</span><span class="sxs-lookup"><span data-stu-id="1a053-119">Specify values for **Client Id**, **Secret Key** and **Tenant Name** field.</span></span>
    
        4. <span data-ttu-id="1a053-120">Clique no botão **Testar Conexão** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="1a053-120">Click **Test Connection** button to test the connection.</span></span>  
  
4.  <span data-ttu-id="1a053-121">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1a053-121">Click **OK** to close the dialog box.</span></span>  
  
    <span data-ttu-id="1a053-122">Você pode ver as propriedades do gerenciador de conexões criado na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="1a053-122">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
