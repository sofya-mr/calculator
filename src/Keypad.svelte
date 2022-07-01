<script>
    import Button from "./Button.svelte";
</script>

<table>
    <tr>
        <td>
            <Button on:printNumber num={"AC"} />
        </td>
        <td>
            <Button on:printNumber num={"-"} />
        </td>
        <td>
            <Button on:printNumber num={"%"}/>
        </td>
        <td>
            <Button on:printNumber num={"/"} action={(a, b) => a / b} />
        </td>
    </tr>
    <tr>
        <td>
            <Button on:printNumber num={7} />
        </td>
        <td>
            <Button on:printNumber num={8} />
        </td>
        <td>
            <Button on:printNumber num={9} />
        </td>
        <td>
            <Button on:printNumber num={"*"} action={(a, b) => a * b} />
        </td>
    </tr>
    <tr>
        <td>
            <Button on:printNumber num={4} />
        </td>
        <td>
            <Button on:printNumber num={5} />
        </td>
        <td>
            <Button on:printNumber num={6} />
        </td>
        <td>
            <Button on:printNumber num={"-"} action={(a, b) => a - b} />
        </td>
    </tr>
    <tr>
        <td>
            <Button on:printNumber num={1} />
        </td>
        <td>
            <Button on:printNumber num={2} />
        </td>
        <td>
            <Button on:printNumber num={3} />
        </td>
        <td>
            <Button on:printNumber num={"+"} action={(a, b) => a + b} />
        </td>
    </tr>
    <tr>
        <td colspan="3">
            <Button on:printNumber num={0} span={2} />
        </td>
        <td colspan="1">
            <Button on:printNumber num={"="} action={(s,v) => v} highlighted={1}/>
        </td>
    </tr>
</table>
