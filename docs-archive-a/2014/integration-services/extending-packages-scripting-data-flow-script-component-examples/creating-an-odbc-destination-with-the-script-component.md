---
title: Criar um destino ODBC com o componente Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], destination components
- ODBC destination [Integration Services]
- destinations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: d198c866-78f4-4a50-ae15-333160645815
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10adff11a7e1db24d9a244c3e83949a010b606c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575223"
---
# <a name="creating-an-odbc-destination-with-the-script-component"></a><span data-ttu-id="626e2-102">Criando um destino ODBC com o componente Script</span><span class="sxs-lookup"><span data-stu-id="626e2-102">Creating an ODBC Destination with the Script Component</span></span>
  <span data-ttu-id="626e2-103">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], você normalmente salva os dados em um destino ODBC usando um destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e o Provedor de Dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para ODBC.</span><span class="sxs-lookup"><span data-stu-id="626e2-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you typically save data to an ODBC destination by using an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for ODBC.</span></span> <span data-ttu-id="626e2-104">Porém, você também pode criar um destino ODBC ad hoc para uso em um único pacote.</span><span class="sxs-lookup"><span data-stu-id="626e2-104">However, you can also create an ad hoc ODBC destination for use in a single package.</span></span> <span data-ttu-id="626e2-105">Para criar esse destino ODBC ad hoc, use o componente Script conforme demonstrado no exemplo seguinte.</span><span class="sxs-lookup"><span data-stu-id="626e2-105">To create this ad hoc ODBC destination, you use the Script component as shown in the following example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="626e2-106">Se desejar criar um componente que possa ser reutilizado mais facilmente em várias tarefas de fluxo de dados e em vários pacotes, procure utilizar o código deste exemplo de componente Script como o ponto inicial de um componente de fluxo de dados personalizado.</span><span class="sxs-lookup"><span data-stu-id="626e2-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="626e2-107">Para obter mais informações, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="626e2-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="626e2-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="626e2-108">Example</span></span>  
 <span data-ttu-id="626e2-109">O exemplo a seguir demonstra como criar um componente de destino que usa um gerenciador de conexões ODBC existente para salvar dados do fluxo de dados em uma tabela do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="626e2-109">The following example demonstrates how to create a destination component that uses an existing ODBC connection manager to save data from the data flow into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="626e2-110">Esse exemplo é uma versão modificada do destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personalizado que foi demonstrado no tópico [Criar um destino com o componente Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="626e2-110">This example is a modified version of the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination that was demonstrated in the topic, [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="626e2-111">Contudo, nesse exemplo, o destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personalizado foi modificado para funcionar com um gerenciador de conexões ODBC e salvar dados em um destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="626e2-111">However, in this example, the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has been modified to work with an ODBC connection manager and save data to an ODBC destination.</span></span> <span data-ttu-id="626e2-112">Essas modificações também incluem as alterações seguintes:</span><span class="sxs-lookup"><span data-stu-id="626e2-112">These modifications also include the following changes:</span></span>  
  
-   <span data-ttu-id="626e2-113">Você não pode chamar o método `AcquireConnection` do gerenciador de conexões ODBC do código gerenciado, porque ele retorna um objeto nativo.</span><span class="sxs-lookup"><span data-stu-id="626e2-113">You cannot call the `AcquireConnection` method of the ODBC connection manager from managed code, because it returns a native object.</span></span> <span data-ttu-id="626e2-114">Portanto, esse exemplo usa a cadeia de conexão do gerenciador de conexões para se conectar à fonte de dados diretamente, usando o Provedor de Dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ODBC gerenciado.</span><span class="sxs-lookup"><span data-stu-id="626e2-114">Therefore, this sample uses the connection string of the connection manager to connect to the data source directly by using the managed ODBC [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider.</span></span>  
  
-   <span data-ttu-id="626e2-115">O `OdbcCommand` espera parâmetros posicionais.</span><span class="sxs-lookup"><span data-stu-id="626e2-115">The `OdbcCommand` expects positional parameters.</span></span> <span data-ttu-id="626e2-116">As posições dos parâmetros são indicadas pelos pontos de interrogação (?) no texto do comando.</span><span class="sxs-lookup"><span data-stu-id="626e2-116">The positions of the parameters are indicated by the question marks (?) in the text of the command.</span></span> <span data-ttu-id="626e2-117">(Por outro lado, um `SqlCommand` espera parâmetros nomeados).</span><span class="sxs-lookup"><span data-stu-id="626e2-117">(In contrast, a `SqlCommand` expects named parameters.)</span></span>  
  
 <span data-ttu-id="626e2-118">Essa amostra usa a tabela **Person.Address** no banco de dados de exemplo **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="626e2-118">This example uses the **Person.Address** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="626e2-119">O exemplo passa a primeira e a quarta colunas, as colunas **int \* AddressID**\* e **nvarchar (30) City** desta tabela por meio do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="626e2-119">The example passes the first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, of this table through the data flow.</span></span> <span data-ttu-id="626e2-120">Esses mesmos dados são usados nas amostras de origem, transformação e destino no tópico [Desenvolvendo tipos específicos de componentes Script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="626e2-120">This same data is used in the source, transformation, and destination samples in the topic, [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="626e2-121">Para configurar esse exemplo de componente Script</span><span class="sxs-lookup"><span data-stu-id="626e2-121">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="626e2-122">Crie um gerenciador de conexões ODBC que se conecte ao banco de dados **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="626e2-122">Create an ODBC connection manager that connects to the **AdventureWorks** database.</span></span>  
  
2.  <span data-ttu-id="626e2-123">Crie uma tabela de destino executando o comando Transact-SQL seguinte no banco de dados **AdventureWorks**:</span><span class="sxs-lookup"><span data-stu-id="626e2-123">Create a destination table by running the following Transact-SQL command in the **AdventureWorks** database:</span></span>  
  
    ```  
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,  
        [City] [nvarchar](30) NOT NULL)  
    ```  
  
3.  <span data-ttu-id="626e2-124">Adicione um novo componente Script à superfície do designer de Fluxo de Dados e configure-o como um destino.</span><span class="sxs-lookup"><span data-stu-id="626e2-124">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>  
  
4.  <span data-ttu-id="626e2-125">Conecte a saída de uma origem ou transformação upstream para o componente de destino no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="626e2-125">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="626e2-126">(Você pode conectar uma origem diretamente a um destino, sem transformações.) Para que essa amostra funcione, a saída do componente upstream deve incluir pelo menos as colunas **AddressID** e **City** da tabela **Person.Address** do banco de dados de exemplo **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="626e2-126">(You can connect a source directly to a destination without any transformations.) To ensure that this sample works, the output of the upstream component must include at least the **AddressID** and **City** columns from the **Person.Address** table of the **AdventureWorks** sample database.</span></span>  
  
5.  <span data-ttu-id="626e2-127">Abra o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="626e2-127">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="626e2-128">Na página **Colunas de Entrada**, selecione as colunas **AddressID** e **City**.</span><span class="sxs-lookup"><span data-stu-id="626e2-128">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>  
  
6.  <span data-ttu-id="626e2-129">Na página **Entradas e Saídas**, renomeie a entrada com um nome mais descritivo, como **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="626e2-129">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>  
  
7.  <span data-ttu-id="626e2-130">Na página **Gerenciadores de Conexões**, adicione ou crie o gerenciador de conexões ODBC com um nome descritivo, como **MyODBCConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="626e2-130">On the **Connection Managers** page, add or create the ODBC connection manager with a descriptive name such as **MyODBCConnectionManager**.</span></span>  
  
8.  <span data-ttu-id="626e2-131">Na página **script** , clique em **Editar script**e insira o script mostrado abaixo na `ScriptMain` classe.</span><span class="sxs-lookup"><span data-stu-id="626e2-131">On the **Script** page, click **Edit Script**, and then enter the script shown below in the `ScriptMain` class.</span></span>  
  
9. <span data-ttu-id="626e2-132">Feche o ambiente de desenvolvimento de script e o **Editor de Transformação Scripts**, então execute a amostra.</span><span class="sxs-lookup"><span data-stu-id="626e2-132">Close the script development environment, close the **Script Transformation Editor**, and then run the sample.</span></span>  
  
    ```vb  
    Imports System.Data.Odbc  
    ...  
    Public Class ScriptMain  
        Inherits UserComponent  
  
        Dim odbcConn As OdbcConnection  
        Dim odbcCmd As OdbcCommand  
        Dim odbcParam As OdbcParameter  
  
        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)  
  
            Dim connectionString As String  
            connectionString = Me.Connections.MyODBCConnectionManager.ConnectionString  
            odbcConn = New OdbcConnection(connectionString)  
            odbcConn.Open()  
  
        End Sub  
  
        Public Overrides Sub PreExecute()  
  
            odbcCmd = New OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " & _  
                "VALUES(?, ?)", odbcConn)  
            odbcParam = New OdbcParameter("@addressid", OdbcType.Int)  
            odbcCmd.Parameters.Add(odbcParam)  
            odbcParam = New OdbcParameter("@city", OdbcType.NVarChar, 30)  
            odbcCmd.Parameters.Add(odbcParam)  
  
        End Sub  
  
        Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)  
  
            With odbcCmd  
                .Parameters("@addressid").Value = Row.AddressID  
                .Parameters("@city").Value = Row.City  
                .ExecuteNonQuery()  
            End With  
  
        End Sub  
  
        Public Overrides Sub ReleaseConnections()  
  
            odbcConn.Close()  
  
        End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System.Data.Odbc;  
    ...  
    public class ScriptMain :  
        UserComponent  
    {  
        OdbcConnection odbcConn;  
        OdbcCommand odbcCmd;  
        OdbcParameter odbcParam;  
  
        public override void AcquireConnections(object Transaction)  
        {  
  
            string connectionString;  
            connectionString = this.Connections.MyODBCConnectionManager.ConnectionString;  
            odbcConn = new OdbcConnection(connectionString);  
            odbcConn.Open();  
  
        }  
  
        public override void PreExecute()  
        {  
  
            odbcCmd = new OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " +  
                "VALUES(?, ?)", odbcConn);  
            odbcParam = new OdbcParameter("@addressid", OdbcType.Int);  
            odbcCmd.Parameters.Add(odbcParam);  
            odbcParam = new OdbcParameter("@city", OdbcType.NVarChar, 30);  
            odbcCmd.Parameters.Add(odbcParam);  
  
        }  
  
        public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)  
        {  
  
            {  
                odbcCmd.Parameters["@addressid"].Value = Row.AddressID;  
                odbcCmd.Parameters["@city"].Value = Row.City;  
                odbcCmd.ExecuteNonQuery();  
            }  
  
        }  
  
        public override void ReleaseConnections()  
        {  
  
            odbcConn.Close();  
  
        }  
    }  
    ```  
  
<span data-ttu-id="626e2-133">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="626e2-133">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="626e2-134">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="626e2-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="626e2-135">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="626e2-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="626e2-136">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="626e2-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626e2-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="626e2-137">See Also</span></span>  
 [<span data-ttu-id="626e2-138">Criando um destino com o componente Script</span><span class="sxs-lookup"><span data-stu-id="626e2-138">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
  
  
