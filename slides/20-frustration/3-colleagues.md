colleagues  


<pre><code class="bash" data-noescape data-trim>
public bool GetResult(VstsService.Response.Release release)
{
    return <mark>release.Environments == null</mark> || release.Environments.All(
        e => e.DeploySteps.All(
            d => e.PreDeployApprovals.All(
                p => p.ApprovedBy<mark>?</mark>.Id != d.LastModifiedBy.Id)));
}
</code></pre>

throwing in some random null checks  

to make an integration test pass...<!-- .element: class="fragment" -->