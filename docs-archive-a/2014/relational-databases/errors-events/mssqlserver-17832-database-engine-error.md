---
title: MSSQLSERVER_17832 | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17828 (Database Engine error)
- maxtokensize
- 17832 (Database Engine error)
- login packet (bad)
ms.assetid: bd56ffe4-0855-4ada-8aca-251fbc6ff2ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dba214e2cce04ff2583e12ae7cee9b54373390a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679387"
---
# <a name="mssqlserver_17832"></a><span data-ttu-id="fb1c9-102">MSSQLSERVER_17832</span><span class="sxs-lookup"><span data-stu-id="fb1c9-102">MSSQLSERVER_17832</span></span>
    
## <a name="details"></a><span data-ttu-id="fb1c9-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fb1c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb1c9-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="fb1c9-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="fb1c9-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fb1c9-105">Event ID</span></span>|<span data-ttu-id="fb1c9-106">17832</span><span class="sxs-lookup"><span data-stu-id="fb1c9-106">17832</span></span>|  
|<span data-ttu-id="fb1c9-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="fb1c9-107">Event Source</span></span>|<span data-ttu-id="fb1c9-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fb1c9-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fb1c9-109">Componente</span><span class="sxs-lookup"><span data-stu-id="fb1c9-109">Component</span></span>|<span data-ttu-id="fb1c9-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fb1c9-110">SQLEngine</span></span>|  
|<span data-ttu-id="fb1c9-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="fb1c9-111">Symbolic Name</span></span>|<span data-ttu-id="fb1c9-112">SRV_BAD_LOGIN_PKT</span><span class="sxs-lookup"><span data-stu-id="fb1c9-112">SRV_BAD_LOGIN_PKT</span></span>|  
|<span data-ttu-id="fb1c9-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fb1c9-113">Message Text</span></span>|<span data-ttu-id="fb1c9-114">O pacote de logon usado para abrir a conexão é estruturalmente inválido; a conexão foi fechada.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-114">The login packet used to open the connection is structurally invalid; the connection has been closed.</span></span> <span data-ttu-id="fb1c9-115">Contate o fornecedor da biblioteca de cliente.%. \* ls</span><span class="sxs-lookup"><span data-stu-id="fb1c9-115">Please contact the vendor of the client library.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb1c9-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="fb1c9-116">Explanation</span></span>  
 <span data-ttu-id="fb1c9-117">O computador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde processar o pacote de logon do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer was unable to process the client login packet.</span></span> <span data-ttu-id="fb1c9-118">Talvez isso ocorra porque o pacote foi criado de modo inadequado ou porque foi danificado durante a transmissão.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-118">This may be because the packet was created improperly or because the packet was damaged during transmission.</span></span> <span data-ttu-id="fb1c9-119">Também pode ocorrer devido à configuração do computador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb1c9-119">It can also be caused by the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="fb1c9-120">O endereço IP listado é o endereço do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-120">The IP address listed is the address of the client computer.</span></span>  
  
### <a name="more-information"></a><span data-ttu-id="fb1c9-121">Mais informações</span><span class="sxs-lookup"><span data-stu-id="fb1c9-121">More Information</span></span>  
 <span data-ttu-id="fb1c9-122">Ao usar a Autenticação Windows em um ambiente Kerberos, um cliente recebe um tíquete Kerberos que contém um Certificado de Atributos de Privilégio (PAC).</span><span class="sxs-lookup"><span data-stu-id="fb1c9-122">When using Windows Authentication in a Kerberos environment, a client receives a Kerberos ticket that contains a Privilege Attribute Certificate (PAC).</span></span> <span data-ttu-id="fb1c9-123">O PAC contém vários tipos de dados de autorização, inclusive grupos dos quais o usuário é membro, direitos que o usuário possui e quais políticas se aplicam ao usuário.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-123">The PAC contains various types of authorization data including groups that the user is a member of, rights the user has, and what policies apply to the user.</span></span> <span data-ttu-id="fb1c9-124">Quando o cliente recebe o tíquete Kerberos, as informações contidas no PAC são usadas para gerar o token de acesso do usuário.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-124">When the client receives the Kerberos ticket, the information contained in the PAC is used to generate the user's access token.</span></span> <span data-ttu-id="fb1c9-125">O cliente apresenta o token ao computador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como parte do pacote de logon.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-125">The client presents the token to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer as part of the login packet.</span></span>  
  
 <span data-ttu-id="fb1c9-126">Se o token foi criado incorretamente ou danificado durante transmissão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode oferecer informações adicionais sobre o problema.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-126">If the token was improperly created or damaged during transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot offer additional information about the problem.</span></span>  
  
 <span data-ttu-id="fb1c9-127">Quando o usuário é membro de muitos grupos ou tem muitas políticas, o token pode ficar maior do que o normal para listar todos esses itens.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-127">When the user is a member of many groups or has many policies, the token may grow larger than normal to list them all.</span></span> <span data-ttu-id="fb1c9-128">Se o token ficar maior que o valor de **MaxTokenSize** do computador servidor, a conexão do cliente falhará com um GNE (Erro Geral de Rede) e um erro 17832 poderá ocorrer.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-128">If the token grows larger than the **MaxTokenSize** value of the server computer, the client fails to connect with a General Network Error (GNE) and error 17832 can occur.</span></span> <span data-ttu-id="fb1c9-129">Este problema pode afetar apenas alguns usuários: usuários com muitos grupos ou políticas.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-129">This problem may affect only some users: users with many groups or policies.</span></span> <span data-ttu-id="fb1c9-130">Quando o problema for o valor de **MaxTokenSize** do computador servidor, o erro 17832 no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será acompanhado por um erro com o estado 9.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-130">When the problem is the **MaxTokenSize** value of the server computer, error 17832 in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log will be accompanied by an error with state 9.</span></span> <span data-ttu-id="fb1c9-131">Para obter mais detalhes sobre o Kerberos e **MaxTokenSize**, consulte [KB327825](https://support.microsoft.com/kb/327825).</span><span class="sxs-lookup"><span data-stu-id="fb1c9-131">For additional details about the Kerberos and **MaxTokenSize**, see [KB327825](https://support.microsoft.com/kb/327825).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb1c9-132">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fb1c9-132">User Action</span></span>  
 <span data-ttu-id="fb1c9-133">Para resolver esse problema, aumente o valor de **MaxTokenSize** do computador servidor para um tamanho grande o suficiente para conter o maior token de qualquer usuário da organização.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-133">To resolve this problem, increase the **MaxTokenSize** value of the server computer, to a size large enough to contain the largest token of any user in your organization.</span></span> <span data-ttu-id="fb1c9-134">Para pesquisar o tamanho de token correto para sua organização, considere o uso do aplicativo **Tokensz**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-134">To research the correct token size for your organization, consider using the **Tokensz** application.</span></span>   
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="fb1c9-135">**Para alterar o MaxTokenSize no computador do servidor**</span><span class="sxs-lookup"><span data-stu-id="fb1c9-135">**To change the MaxTokenSize  on the server computer**</span></span>  
  
1.  <span data-ttu-id="fb1c9-136">No menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-136">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="fb1c9-137">Digite `regedit` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-137">Type `regedit`, and then click **OK**.</span></span> <span data-ttu-id="fb1c9-138">(Se a caixa de diálogo **Controle de Conta de Usuário** for exibida, clique em **Continuar**.)</span><span class="sxs-lookup"><span data-stu-id="fb1c9-138">(If the **User Account Control** dialog box appears, click **Continue**.)</span></span>  
  
3.  <span data-ttu-id="fb1c9-139">Navegue para **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-139">Navigate to **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span></span>  
  
4.  <span data-ttu-id="fb1c9-140">Se o parâmetro **MaxTokenSize** não estiver presente, clique com o botão direito do mouse em **Parâmetros**, aponte para **Novo** e clique no Valor **DWORD (32 bits)** .</span><span class="sxs-lookup"><span data-stu-id="fb1c9-140">If the **MaxTokenSize** parameter is not present, right-click **Parameters**, point to **New**, and then click **DWORD (32-bit)** Value.</span></span> <span data-ttu-id="fb1c9-141">Nomeie a entrada de Registro **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-141">Name the registry entry **MaxTokenSize**.</span></span>  
  
5.  <span data-ttu-id="fb1c9-142">Clique com o botão direito do mouse em **MaxTokenSize** e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-142">Right-click **MaxTokenSize**, and then click **Modify**.</span></span>  
  
6.  <span data-ttu-id="fb1c9-143">Na caixa **Dados de valor**, digite o valor desejado de **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-143">In the **Value data** box type the desired **MaxTokenSize** value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb1c9-144">O valor hexadecimal ffff (valor decimal 65535) corresponde ao tamanho de token máximo recomendado.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-144">Hexadecimal value ffff (decimal value 65535) is the maximum recommended token size.</span></span> <span data-ttu-id="fb1c9-145">O fornecimento desse valor provavelmente resolverá o problema, mas talvez tenha efeitos negativos no computador em relação ao desempenho.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-145">Providing this value would probably solve the problem, but could have negative computer-wide effects with regard to performance.</span></span> <span data-ttu-id="fb1c9-146">Recomendamos que você estabeleça o valor mínimo de **MaxTokenSize** que permita o maior token de qualquer usuário da organização e insira esse valor.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-146">We recommend that you establish the minimum **MaxTokenSize** value that allows for the largest token of any user in your organization and enter that value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="fb1c9-147">Feche o **Editor do Registro**.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-147">Close **Registry Editor**.</span></span>  
  
9. <span data-ttu-id="fb1c9-148">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="fb1c9-148">Restart the computer.</span></span>  
  
  
