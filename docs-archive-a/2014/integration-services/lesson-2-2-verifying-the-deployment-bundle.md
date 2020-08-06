---
title: 'Etapa 2: verificar o pacote de implantação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f452a87154175ac05a050761d8f12b6bfe61cd8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570119"
---
# <a name="step-2-verifying-the-deployment-bundle"></a><span data-ttu-id="74477-102">Etapa 2: Verificar o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="74477-102">Step 2: Verifying the Deployment Bundle</span></span>
  <span data-ttu-id="74477-103">Na lição 1, você criou o projeto do Tutorial de Implantação e adicionou pacotes e arquivos auxiliares ao projeto; na tarefa anterior você compilou um utilitário de implantação para o projeto.</span><span class="sxs-lookup"><span data-stu-id="74477-103">In lesson 1, you created the Deployment Tutorial project and added packages and ancillary files to the project; in the previous task you built a deployment utility for the project.</span></span>  
  
 <span data-ttu-id="74477-104">Nesta tarefa, você verificará o conteúdo do pacote de implantação.</span><span class="sxs-lookup"><span data-stu-id="74477-104">In this task, you will verify the contents of the deployment bundle.</span></span> <span data-ttu-id="74477-105">O pacote de implantação é a pasta que você copiará para o computador de destino e usará para instalar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="74477-105">The deployment bundle is the folder that you will copy to the destination computer and use to install packages.</span></span> <span data-ttu-id="74477-106">Se você tiver usado o valor padrão – bin\Deployment – como a localização do utilitário de implantação, o pacote de implantação será a pasta Bin\Deployment dentro da pasta Tutorial de Implantação no projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74477-106">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a><span data-ttu-id="74477-107">Para verificar o conteúdo do pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="74477-107">To verify the content of deployment bundle</span></span>  
  
1.  <span data-ttu-id="74477-108">Localize a pasta bin\Deployment em seu computador.</span><span class="sxs-lookup"><span data-stu-id="74477-108">Locate the bin\Deployment folder on your computer.</span></span>  
  
2.  <span data-ttu-id="74477-109">Verifique se os seguintes arquivos estão presentes:</span><span class="sxs-lookup"><span data-stu-id="74477-109">Verify that the following files are present:</span></span>  
  
    -   <span data-ttu-id="74477-110">DataTransfer.dtsx</span><span class="sxs-lookup"><span data-stu-id="74477-110">DataTransfer.dtsx</span></span>  
  
    -   <span data-ttu-id="74477-111">datatransferconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="74477-111">datatransferconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="74477-112">Deployment Tutorial.SSISDeploymentManifest</span><span class="sxs-lookup"><span data-stu-id="74477-112">Deployment Tutorial.SSISDeploymentManifest</span></span>  
  
    -   <span data-ttu-id="74477-113">LoadXMLData.dtsx</span><span class="sxs-lookup"><span data-stu-id="74477-113">LoadXMLData.dtsx</span></span>  
  
    -   <span data-ttu-id="74477-114">loadxmldataconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="74477-114">loadxmldataconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="74477-115">NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="74477-115">NewCustomers.txt</span></span>  
  
    -   <span data-ttu-id="74477-116">orders.xml</span><span class="sxs-lookup"><span data-stu-id="74477-116">orders.xml</span></span>  
  
    -   <span data-ttu-id="74477-117">orders.xsd</span><span class="sxs-lookup"><span data-stu-id="74477-117">orders.xsd</span></span>  
  
    -   <span data-ttu-id="74477-118">Readme.txt</span><span class="sxs-lookup"><span data-stu-id="74477-118">Readme.txt</span></span>  
  
3.  <span data-ttu-id="74477-119">Clique com o botão direito do mouse em Deployment Tutorial.SSISDeploymentManifest, aponte para **Abrir Com**e clique em **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="74477-119">Right-click Deployment Tutorial.SSISDeploymentManifest, point **to Open With**, and then click **Internet Explorer**.</span></span> <span data-ttu-id="74477-120">Você também pode abrir o arquivo em um editor de textos como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="74477-120">You can also open the file in a text editor such as Notepad.</span></span> <span data-ttu-id="74477-121">O código XML do arquivo deve ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74477-121">The XML code of the file should be the following:</span></span>  
  
     `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  <span data-ttu-id="74477-122">Verifique se o valor do `AllowConfigurationChanges` atributo é **true** e se o XML inclui um `Package` elemento para cada um dos dois pacotes, um `MiscellaneousFile` elemento para cada um dos quatro arquivos que não são de pacote e um `ConfigurationFile` elemento para cada um dos dois arquivos de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="74477-122">Verify that the value of the `AllowConfigurationChanges` attribute is **true** and the XML includes a `Package` element for each of the two packages, a `MiscellaneousFile` element for each of the four non-package files, and a `ConfigurationFile` element for each of the two XML configuration files.</span></span>  
  
5.  <span data-ttu-id="74477-123">Saia do Internet Explorer ou do editor de textos.</span><span class="sxs-lookup"><span data-stu-id="74477-123">Exit Internet Explorer or the text editor.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="74477-124">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="74477-124">Next Lesson</span></span>  
 [<span data-ttu-id="74477-125">Lição 3: Instalando pacotes</span><span class="sxs-lookup"><span data-stu-id="74477-125">Lesson 3: Installing Packages</span></span>](../integration-services/lesson-3-install-ssis-package.md)  
  
<span data-ttu-id="74477-126">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="74477-126">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="74477-127">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="74477-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="74477-128">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="74477-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="74477-129">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="74477-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
