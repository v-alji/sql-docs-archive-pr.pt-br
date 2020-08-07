---
title: Barra de status (Editor de Consultas do Mecanismo de Banco de Dados)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7f2d6f4-bb94-4cf5-a096-c34397e679af
author: rothja
ms.author: jroth
ms.openlocfilehash: 743ae0a4152daee19aa67f85337ae4077a3ed7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581751"
---
# <a name="status-bar-database-engine-query-editor"></a><span data-ttu-id="2c098-102">Barra de status (Editor de Consultas do Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="2c098-102">Status Bar (Database Engine Query Editor)</span></span>
  <span data-ttu-id="2c098-103">A barra de status das janelas do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] podem ser codificadas por cor para indicar a qual instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] cada janela está conectada.</span><span class="sxs-lookup"><span data-stu-id="2c098-103">The status bar of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor windows can be color coded to indicate which instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] each window is connected to.</span></span>  
  
1.  <span data-ttu-id="2c098-104">**Antes de começar:**  [Cores da Barra de Status](#StatusBarColors)</span><span class="sxs-lookup"><span data-stu-id="2c098-104">**Before you begin:**  [Status Bar Colors](#StatusBarColors)</span></span>  
  
2.  <span data-ttu-id="2c098-105">**Para definir uma cor de status do servidor em:**  [Pesquisador de Objetos](#SetOEServerColor), [Servidor Registrado](#SetRegServerColor)</span><span class="sxs-lookup"><span data-stu-id="2c098-105">**To set a server status color in:**  [Object Explorer](#SetOEServerColor), [Registered Server](#SetRegServerColor)</span></span>  
  
3.  <span data-ttu-id="2c098-106">**Para usar uma cor de status:**  [Abrir o Editor de Consultas, usando uma cor de servidor](#OpenServerColor), [Abrir o Editor de Consultas, especificando uma cor de status](#OpenSpecColor)</span><span class="sxs-lookup"><span data-stu-id="2c098-106">**To use a status color:**  [Open Query Editor Using a Server Color](#OpenServerColor), [Open a Query Editor Specifying a Status Color](#OpenSpecColor)</span></span>  
  
##  <a name="status-bar-colors"></a><a name="StatusBarColors"></a> <span data-ttu-id="2c098-107">Cores da barra de status</span><span class="sxs-lookup"><span data-stu-id="2c098-107">Status Bar Colors</span></span>  
 <span data-ttu-id="2c098-108">Você pode associar uma cor de barra de status a um nó de servidor específico em **Pesquisador de Objetos** ou **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="2c098-108">You can associate a status bar color with a specific server node in either **Object Explorer** or **Registered Servers**.</span></span> <span data-ttu-id="2c098-109">As cores podem ser especificadas somente para nós de servidor conectados a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)], e não para nós de servidor de outras tecnologias do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c098-109">The colors can only be specified for server nodes connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], not server nodes for other SQL Server technologies.</span></span> <span data-ttu-id="2c098-110">Você também pode especificar uma cor de barra de status personalizada sempre que você conecta uma nova janela do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c098-110">You can also specify a custom status bar color each time you connect a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2c098-111">Em seguida, você pode abrir uma janela do Editor de Consultas usando a cor de status definida para o nó do servidor ou especificar uma cor exclusiva para essa janela do editor.</span><span class="sxs-lookup"><span data-stu-id="2c098-111">You can then open a query editor window using either the status color defined for the server node, or specify a unique color for that editor window.</span></span>  
  
 <span data-ttu-id="2c098-112">A definição de uma cor de barra de status personalizada para um nó de servidor no Pesquisador de Objetos deve ser feita durante o estabelecimento da conexão.</span><span class="sxs-lookup"><span data-stu-id="2c098-112">Setting a custom status bar color for a server node in Object Explorer must be done when making the connection.</span></span> <span data-ttu-id="2c098-113">Para alterar a cor associada a um nó de servidor existente, desconecte e reconecte especificando a nova cor.</span><span class="sxs-lookup"><span data-stu-id="2c098-113">To change the color associated with an existing server node, you must disconnect and then reconnect specifying the new color.</span></span>  
  
##  <a name="set-the-status-color-for-a-server-in-object-explorer"></a><a name="SetOEServerColor"></a> <span data-ttu-id="2c098-114">Definir a cor de status para um servidor no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="2c098-114">Set the Status Color for a Server in Object Explorer</span></span>  
 <span data-ttu-id="2c098-115">**Para definir uma cor de status no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="2c098-115">**To set a server status color in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="2c098-116">No **Pesquisador de Objetos**, selecione o botão **Conectar** e depois a opção **Mecanismo de Banco de Dados...** .</span><span class="sxs-lookup"><span data-stu-id="2c098-116">In **Object Explorer**, select the **Connect** button and then select **Database Engine...**.</span></span>  
  
2.  <span data-ttu-id="2c098-117">Na caixa de diálogo **Conectar ao Servidor**, selecione **Opções >>** .</span><span class="sxs-lookup"><span data-stu-id="2c098-117">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
3.  <span data-ttu-id="2c098-118">Marque a caixa de seleção **Usar cor personalizada** .</span><span class="sxs-lookup"><span data-stu-id="2c098-118">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="2c098-119">Para selecionar a cor, selecione o botão **Selecionar...** .</span><span class="sxs-lookup"><span data-stu-id="2c098-119">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="2c098-120">Selecione uma cor básica ou personalizada e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2c098-120">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="2c098-121">Preencha o restante das informações de conexão e selecione o botão **Conectar** .</span><span class="sxs-lookup"><span data-stu-id="2c098-121">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
##  <a name="set-the-status-color-for-a-registered-server"></a><a name="SetRegServerColor"></a> <span data-ttu-id="2c098-122">Definir a cor de status para um servidor registrado</span><span class="sxs-lookup"><span data-stu-id="2c098-122">Set the Status Color For a Registered Server</span></span>  
 <span data-ttu-id="2c098-123">**Par definir uma cor de status para um servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="2c098-123">**To set a server color For a Registered Server**</span></span>  
  
1.  <span data-ttu-id="2c098-124">Em **Servidores Registrados**, clique com o botão direito do mouse no nó de servidor e selecione **Propriedades...** .</span><span class="sxs-lookup"><span data-stu-id="2c098-124">In **Registered Servers**, right click the server node and then select **Properties...**.</span></span>  
  
2.  <span data-ttu-id="2c098-125">Na caixa de diálogo **Editar Propriedades de Registro do Servidor** , selecione a guia **Propriedades de Conexão** .</span><span class="sxs-lookup"><span data-stu-id="2c098-125">On the **Edit Server Registration Properties** dialog, select the **Connection Properties** tab.</span></span>  
  
3.  <span data-ttu-id="2c098-126">Marque a caixa de seleção **Usar cor personalizada** .</span><span class="sxs-lookup"><span data-stu-id="2c098-126">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="2c098-127">Para selecionar a cor, selecione o botão **Selecionar...** .</span><span class="sxs-lookup"><span data-stu-id="2c098-127">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="2c098-128">Selecione uma cor básica ou personalizada e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2c098-128">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="2c098-129">Selecione o botão **Salvar** na caixa de diálogo **Editar Propriedades de Registro do Servidor** .</span><span class="sxs-lookup"><span data-stu-id="2c098-129">Select the **Save** button on the **Edit Server Registration Properties** dialog.</span></span>  
  
##  <a name="open-an-editor-using-a-server-color"></a><a name="OpenServerColor"></a> <span data-ttu-id="2c098-130">Abrir um editor usando uma cor de servidor</span><span class="sxs-lookup"><span data-stu-id="2c098-130">Open An Editor Using a Server Color</span></span>  
 <span data-ttu-id="2c098-131">**Para abrir uma janela do editor usando uma cor de servidor**</span><span class="sxs-lookup"><span data-stu-id="2c098-131">**To open an editor window using a server color**</span></span>  
  
-   <span data-ttu-id="2c098-132">Clique com o botão direito do mouse em um nó de servidor no **Pesquisador de Objetos** ou em **Servidores Registrados**e selecione **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2c098-132">Right-click a server node in either **Object Explorer** or **Registered Servers**, and select **New Query**.</span></span>  
  
-   <span data-ttu-id="2c098-133">Opcionalmente, realce um nó de servidor e selecione o botão **Nova Consulta** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="2c098-133">Alternatively, highlight a server node, and then select the **New Query** toolbar button.</span></span>  
  
-   <span data-ttu-id="2c098-134">A barra de status da janela do editor usará a cor definida para o servidor associado.</span><span class="sxs-lookup"><span data-stu-id="2c098-134">The status bar in the editor window will use the color defined for the associated server.</span></span>  
  
##  <a name="open-an-editor-specifying-a-status-color"></a><a name="OpenSpecColor"></a> <span data-ttu-id="2c098-135">Abrir um editor especificando uma cor de status</span><span class="sxs-lookup"><span data-stu-id="2c098-135">Open an Editor Specifying a Status Color</span></span>  
 <span data-ttu-id="2c098-136">**Para abrir uma janela do editor especificando uma cor de status**</span><span class="sxs-lookup"><span data-stu-id="2c098-136">**To open an editor window specifying a status color**</span></span>  
  
-   <span data-ttu-id="2c098-137">Abra o menu **Arquivo** , selecione **Novo**e, em seguida, selecione **Consulta do Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="2c098-137">Open the **File** menu, select **New**, and then select **Database Engine Query**.</span></span>  
  
-   <span data-ttu-id="2c098-138">Na caixa de diálogo **Conectar ao Servidor**, selecione **Opções >>** .</span><span class="sxs-lookup"><span data-stu-id="2c098-138">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
-   <span data-ttu-id="2c098-139">Marque a caixa de seleção **Usar cor personalizada** .</span><span class="sxs-lookup"><span data-stu-id="2c098-139">Select the **Use custom color** check box.</span></span>  
  
-   <span data-ttu-id="2c098-140">Para selecionar a cor, selecione o botão **Selecionar...** .</span><span class="sxs-lookup"><span data-stu-id="2c098-140">To select the color, select the **Select...** button.</span></span>  
  
-   <span data-ttu-id="2c098-141">Selecione uma cor básica ou personalizada e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2c098-141">Select either a basic or custom color, then select OK.</span></span>  
  
-   <span data-ttu-id="2c098-142">Preencha o restante das informações de conexão e selecione o botão **Conectar** .</span><span class="sxs-lookup"><span data-stu-id="2c098-142">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c098-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c098-143">See Also</span></span>  
 [<span data-ttu-id="2c098-144">Editores de consultas e de texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2c098-144">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
