                    <div class="playerTeam">{player.home.pos != "DEF" ? player.home.team : ""}</div>
                            {/if}
                        {/if}
                    </div>
                    <span class="points pointsR">{round(player.home.points)}<div class="totalProjection">{round(player.home.projection)}</div></span>
                </div>

                <div class="dividerLine" />

                <div class="player playerAway">
                    <span class="iconAndTeam iconAndTeamAway">
                        {#if player.away.avatar}
                            <div class="playerAvatar playerInfo" style="{player.away.avatar}" />
                        {/if}
                        {#if player.away.pos}
                            <span class="pos {player.away.pos}">{player.away.pos}</span>
                        {/if}
                    </span>
                    <div class="nameHolder nameHolderR{player.away.name == 'Empty'? ' playerEmpty' : ''}">
                        {#if player.away.team}
                            {#if player.away.opponent}
                                <div class="playerTeam">{player.away.opponent} vs{player.away.pos != "DEF" ? ` ${player.away.team}` : ""}</div>
                            {:else}
                                <div class="playerTeam">{player.away.pos != "DEF" ? player.away.team : ""}</div>
                            {/if}
                        {/if}
                        <span class="playerInfo playerName playerNameAway">{player.away.name}</span>
                    </div>
                    <span class="points pointsL">{round(player.away.points)}<div class="totalProjection">{round(player.away.projection)}</div></span>
                </div>
            </div>
        {/each}
        {#if !expandOverride}
            <div class="close" on:click={() => expandClose()}>Close Matchup</div>
        {/if}
    </div>
</div>
