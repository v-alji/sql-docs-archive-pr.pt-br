---
title: Assinar um pacote usando um certificado digital | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- digital signatures [Integration Services]
- signing packages [Integration Services]
- signatures [Integration Services]
ms.assetid: 182b115e-0fe2-4717-8dff-183f9eb6e397
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bd0f73d609623f882e474c96a01cd3bc0274b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685825"
---
# <a name="sign-a-package-by-using-a-digital-certificate"></a><span data-ttu-id="e63dc-102">Assinar um pacote por meio de um certificado digital</span><span class="sxs-lookup"><span data-stu-id="e63dc-102">Sign a Package by Using a Digital Certificate</span></span>
  <span data-ttu-id="e63dc-103">Este tópico descreve como assinar um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] com um certificado digital.</span><span class="sxs-lookup"><span data-stu-id="e63dc-103">This topic describes how to sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package with a digital certificate.</span></span> <span data-ttu-id="e63dc-104">Você pode usar uma assinatura digital, junto com outras configurações, para evitar o carregamento e a execução de um pacote inválido.</span><span class="sxs-lookup"><span data-stu-id="e63dc-104">You can use a digital signature, together with other settings, to prevent a package that is not valid from loading and running.</span></span>  
  
 <span data-ttu-id="e63dc-105">Antes de poder assinar um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , você deve realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="e63dc-105">Before you can sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, you must do the following tasks:</span></span>  
  
-   <span data-ttu-id="e63dc-106">Criar ou obter uma chave privada a ser associada ao certificado e armazenar esta chave no computador local.</span><span class="sxs-lookup"><span data-stu-id="e63dc-106">Create or obtain a private key to associate with the certificate, and store this private key on the local computer.</span></span>  
  
-   <span data-ttu-id="e63dc-107">Obter um certificado com a finalidade de assinatura de código de uma autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="e63dc-107">Obtain a certificate for the purpose of code signing from a trusted certification authority.</span></span> <span data-ttu-id="e63dc-108">Você pode usar um dos métodos a seguir para obter ou criar um certificado:</span><span class="sxs-lookup"><span data-stu-id="e63dc-108">You can use one of the following methods to obtain or create a certificate:</span></span>  
  
    -   <span data-ttu-id="e63dc-109">Obtenha um certificado de uma autoridade de certificação comercial pública que emite certificados.</span><span class="sxs-lookup"><span data-stu-id="e63dc-109">Obtain a certificate from a public, commercial certification authority that issues certificates.</span></span>  
  
    -   <span data-ttu-id="e63dc-110">Obtenha um certificado de um servidor de certificados, que permita que uma organização emita certificados internamente.</span><span class="sxs-lookup"><span data-stu-id="e63dc-110">Obtain a certificate from a certificate server, that enables an organization to internally issue certificates.</span></span> <span data-ttu-id="e63dc-111">É necessário adicionar o certificado raiz usado para assinar o certificado ao armazenamento **Autoridades de Certificação Raiz Confiáveis** .</span><span class="sxs-lookup"><span data-stu-id="e63dc-111">You have to add the root certificate that is used to sign the certificate to the **Trusted Root Certification Authorities** store.</span></span> <span data-ttu-id="e63dc-112">Para adicionar o certificado raiz, você pode usar o snap-in de Certificados para o [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="e63dc-112">To add the root certificate, you can use the Certificates snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="e63dc-113">Para obter mais informações, consulte o tópico “[Serviços de certificado](https://go.microsoft.com/fwlink/?LinkId=100755)” na biblioteca do MSDN.</span><span class="sxs-lookup"><span data-stu-id="e63dc-113">For more information, see the topic, "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)," in the MSDN library.</span></span>  
  
    -   <span data-ttu-id="e63dc-114">Crie seu próprio certificado somente para teste.</span><span class="sxs-lookup"><span data-stu-id="e63dc-114">Create your own certificate for testing purposes only.</span></span> <span data-ttu-id="e63dc-115">A Ferramenta de Criação de Certificado (Makecert.exe) gera certificados X.509 para teste.</span><span class="sxs-lookup"><span data-stu-id="e63dc-115">The Certificate Creation Tool (Makecert.exe) generates X.509 certificates for testing purposes.</span></span> <span data-ttu-id="e63dc-116">Para obter mais informações, consulte o tópico “[Ferramenta de Criação de Certificado (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)” na Biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="e63dc-116">For more information, see the topic, "[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)," in the MSDN Library.</span></span>  
  
     <span data-ttu-id="e63dc-117">Para obter mais informações sobre certificados, consulte a Ajuda online do snap-in de Certificados.</span><span class="sxs-lookup"><span data-stu-id="e63dc-117">For more information about certificates, see the online Help for the Certificates snap-in.</span></span> <span data-ttu-id="e63dc-118">Para obter mais informações sobre como assinar ativos digitais, consulte o tópico “[Assinando e verificando o código com o Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)” na biblioteca do MSDN.</span><span class="sxs-lookup"><span data-stu-id="e63dc-118">For more information about how to sign digital assets, see the topic, "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)," in the MSDN Library.</span></span>  
  
-   <span data-ttu-id="e63dc-119">Verifique se o certificado foi habilitado para assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="e63dc-119">Make sure that the certificate has been enabled for code signing.</span></span> <span data-ttu-id="e63dc-120">Para saber se um certificado está habilitado para assinatura de código, revise as propriedades do certificado no snap-in de Certificados.</span><span class="sxs-lookup"><span data-stu-id="e63dc-120">To determine whether a certificate is enabled for code signing, review the properties of the certificate in the Certificates snap-in.</span></span>  
  
-   <span data-ttu-id="e63dc-121">Armazene o certificado no armazenamento Pessoal.</span><span class="sxs-lookup"><span data-stu-id="e63dc-121">Store the certificate in the Personal store.</span></span>  
  
 <span data-ttu-id="e63dc-122">Depois de concluir as tarefas anteriores, realize o procedimento a seguir para assinar um pacote.</span><span class="sxs-lookup"><span data-stu-id="e63dc-122">After you have completed the previous tasks, you can use the following procedure to sign a package.</span></span>  
  
### <a name="to-sign-a-package"></a><span data-ttu-id="e63dc-123">Para assinar um pacote</span><span class="sxs-lookup"><span data-stu-id="e63dc-123">To sign a package</span></span>  
  
1.  <span data-ttu-id="e63dc-124">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote a ser assinado.</span><span class="sxs-lookup"><span data-stu-id="e63dc-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to be signed.</span></span>  
  
2.  <span data-ttu-id="e63dc-125">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="e63dc-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e63dc-126">No [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, no menu **SSIS** , clique em **Assinatura Digital**.</span><span class="sxs-lookup"><span data-stu-id="e63dc-126">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, on the **SSIS** menu, click **Digital Signing**.</span></span>  
  
4.  <span data-ttu-id="e63dc-127">Na caixa de diálogo **Assinatura Digital** , clique em **Assinar**.</span><span class="sxs-lookup"><span data-stu-id="e63dc-127">In the **Digital Signing** dialog box, click **Sign**.</span></span>  
  
5.  <span data-ttu-id="e63dc-128">Na caixa de diálogo **Selecionar um Certificado** , selecione um certificado.</span><span class="sxs-lookup"><span data-stu-id="e63dc-128">In the **Select a Certificate** dialog box, select a certificate.</span></span>  
  
6.  <span data-ttu-id="e63dc-129">(Opcional) Clique em **Exibir Certificado**para exibir informações do certificado.</span><span class="sxs-lookup"><span data-stu-id="e63dc-129">(Optional) Click **View Certificat**e to view certificate information.</span></span>  
  
7.  <span data-ttu-id="e63dc-130">Clique em **OK** para fechar a caixa de diálogo **Selecionar um Certificado** .</span><span class="sxs-lookup"><span data-stu-id="e63dc-130">Click **OK** to close the **Select a Certificate** dialog box.</span></span>  
  
8.  <span data-ttu-id="e63dc-131">Clique em **OK** para fechar a caixa de diálogo **Assinatura Digital** .</span><span class="sxs-lookup"><span data-stu-id="e63dc-131">Click **OK** to close the **Digital Signing** dialog box.</span></span>  
  
9. <span data-ttu-id="e63dc-132">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="e63dc-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
     <span data-ttu-id="e63dc-133">Embora o pacote tenha sido assinado, é necessário configurar o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para verificar a assinatura digital antes de carregar o pacote.</span><span class="sxs-lookup"><span data-stu-id="e63dc-133">Although the package has been signed, you must now configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] to check or verify the digital signature before loading the package.</span></span> <span data-ttu-id="e63dc-134">Para obter mais informações, consulte [Identificar a origem de pacotes com assinaturas digitais](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="e63dc-134">For more information, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e63dc-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e63dc-135">See Also</span></span>  
 [<span data-ttu-id="e63dc-136">Visão geral de segurança &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e63dc-136">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
